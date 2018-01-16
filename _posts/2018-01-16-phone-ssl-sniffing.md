---
date: '2018-01-16T03:10:00.001-0700'
tags: linux 
---

Introduction
============

After summarizing how SSL/TLS works, we present methods generally used
to decrypt the encrypted traffic. A method based on a SSL proxy is
detailed, and that method is particularly well suited to reverse
engineer the calls a mobile phone app uses to talk to a server.

SSL encryption
==============

The protocol
------------

SSL and its successor TLS are protocols defined in RFCs. For instance
TLSv2 is defined in RFC5246 @rfc5246. The protocol used public key and
conventional encryption techniques, and achieves both a high level of
security and high performance. The picture \[sslfig\] summarizes the
uses of public key (slow) and conventional (fast) cryptography
techniques. To simplify, public key cryptography is used to agree on a
secret key (or a sequence of secret keys) that are then used to encrypt
the network traffic.

\[sslfig\]

The case of a web app
---------------------

In the case of a webapp, you can use network dumpers (like tcpdump or
wireshark) and then decrypt the resulting PCAP files using two
techniques @stuart2012:

-   Method 1 : Decrypting the traffic with the server private key. This
    method is rarely used as the server private key is rarely available
    for distribution.

-   Method 2: Decrypting with Pre-Master Secrets. This generates in a
    log file defined by the SSLKEYLOGFILE variable that contains the
    sequences of secrets. This works well with firefox or chrome.

The case of an android app
--------------------------

In the case of an android app, the control over the client is usually
restricted. I.e, it’s much harder to put the network interfaces in
promiscuous mode to “sniff” the network traffic. In that case a second
class of network analysis tools are more adapted: proxies. There are two
types of proxies: explicit and transparent.

Explicit proxies expect a HTTP load that respect the HTTP proxy
protocol. Configuring proxies has been made more difficult by Google in
android @androidissue37068375 and proxy applications like “Proxy
Settings”@proxysettingsapp do not work anymore from Android 6
(marshmallow).

Transparent proxies on the other hand do not require the client to be
configured to use a proxy: they just require that the normal HTTP and
HTTP traffic flows through them.

The “how mitmproxy works” page @howmitmproxy details how a SSL
transparent proxy works. One of the key point is that the client needs
to trust the proxy CA certificate.

The following describes the details on setting mitmproxy to decode the
SSL traffic from my android samsung phone @chmod0002016 @heckel2013.

The VPN
=======

Installation of pptpd on the server
-----------------------------------

I use as VPN server a bare metal server hosted in Germany with heztner,
IP 5.9.136.58 and running Debian Linux.

    apt-get install pptpd

Edit /etc/pptpd.conf and add:

    localip 5.9.136.58
    remoteip 10.68.68.1-62

Edit the /etc/ppp/pptpd-options file such that:

    # egrep -v '^#.*' /etc/ppp/pptpd-options  | egrep -v '^$'
    name madon.net
    refuse-pap
    refuse-chap
    refuse-mschap
    require-mschap-v2
    require-mppe-128
    nomppe-40
    nodefaultroute
    debug
    dump
    lock
    nobsdcomp 
    auth

and write some credentials in /etc/ppp/chap-secrets

    # Secrets for authentication using CHAP
    # client    server  secret          IP addresses
    MYUSERNAME  *   MYPASSWORD  *

Start pptpd with the new configuration:

    systemctl restart pptpd

VPN iptables rules
------------------

Make sure that your iptables rules allow inbound client to connect to
the VPN server. In my case I had to have:

    iptables -A INPUT -p tcp --dport 1723 -j ACCEPT
    iptables -A INPUT -p gre -j ACCEPT

For more information on iptables, see Appendix \[netfilter\]

Client (android) configuration
------------------------------

In the “Settings” - “Network” - “More Network” menu of your android
phone, create a new PPTP VPN using the server just created and the
credentials defined on the server.

Validating the connection
-------------------------

Try to connect your phone pressing on the VPN name. The logs below show
a successful connection:


    Nov 14 18:33:49 user10 pptpd[4500]: CTRL: Starting call (launching pppd, opening GRE)
    Nov 14 18:33:49 user10 pptpd[4500]: GRE: Bad checksum from pppd.
    Nov 14 18:33:49 user10 pppd[4501]: using channel 10
    Nov 14 18:33:49 user10 pppd[4501]: sent [LCP ConfReq id=0x1 <asyncmap 0x0> <auth chap MS-v2> <magic 0x7ff4dff8> <pcomp> <accomp>]
    Nov 14 18:33:49 user10 pppd[4501]: rcvd [LCP ConfReq id=0x1 <mru 1400> <asyncmap 0x0> <magic 0xd2fbdc1d> <pcomp> <accomp>]
    Nov 14 18:33:49 user10 pppd[4501]: sent [LCP ConfAck id=0x1 <mru 1400> <asyncmap 0x0> <magic 0xd2fbdc1d> <pcomp> <accomp>]
    Nov 14 18:33:49 user10 pppd[4501]: rcvd [LCP ConfAck id=0x1 <asyncmap 0x0> <auth chap MS-v2> <magic 0x7ff4dff8> <pcomp> <accomp>]
    Nov 14 18:33:49 user10 pppd[4501]: sent [LCP EchoReq id=0x0 magic=0x7ff4dff8]
    Nov 14 18:33:49 user10 pppd[4501]: sent [CHAP Challenge id=0x4e <c68e3f6d67d5887ee32df17c36b08e9f>, name = "madon.net"]
    Nov 14 18:33:49 user10 pppd[4501]: rcvd [LCP EchoRep id=0x0 magic=0xd2fbdc1d]
    Nov 14 18:33:49 user10 pppd[4501]: rcvd [CHAP Response id=0x4e <75abc5e31e901dfe5319c2c2f8f5d9d1000000000000000037b386d015d6676316db7c9eeee73a524548caf94c24344100>, name = "androidtester"]
    Nov 14 18:33:49 user10 pppd[4501]: sent [CHAP Success id=0x4e "S=362214BA7301AEB55AC666EDCC419F96454ED749 M=Access granted"]
    ....
    Nov 14 18:33:49 user10 pppd[4501]: local  IP address 5.9.136.58
    Nov 14 18:33:49 user10 pppd[4501]: remote IP address 10.68.68.234
    Nov 14 18:33:49 user10 pppd[4501]: pptpd-logwtmp.so ip-up ppp0 androidtester 92.171.77.212
    Nov 14 18:33:49 user10 pppd[4501]: Script /etc/ppp/ip-up started (pid 4538)
    Nov 14 18:33:50 user10 pppd[4501]: Script /etc/ppp/ip-up finished (pid 4538), status = 0x0

At this stage, your phone is connected to the VPN but cannot go out of
the VPN server to the Internet.

The SSL proxy
=============

Installation of mitmproxy
-------------------------

Install mitmproxy as per @installmitmproxy

    apt-get install python3-dev python3-pip libffi-dev libssl-dev
    pip3 install mitmproxy 

routing and iptables rules
--------------------------

    sysctl -w net.inet.ip.forwarding=1
    # (or echo 1 > /proc/sys/net/ipv4/ip_forward )
    iptables -t nat -A PREROUTING -p tcp --destination-port 80 -j REDIRECT --to-ports 8080
    iptables -t nat -A PREROUTING -p tcp --destination-port 443 -j REDIRECT --to-ports 8080

You also may need depending on your iptables POLICY:

    iptables -A INPUT -p tcp --dport 80 -s 10.68.68.1 -j ACCEPT
    iptables -A INPUT -p tcp --dport 8080 -s 10.68.68.1 -j ACCEPT

Start mitmproxy (or mitmdump)
-----------------------------

At this stage you should see your phone traffic going through the proxy,
but with a certificate error:

    mitmdump -T -v 
    Proxy server listening at http://0.0.0.0:8080
    10.68.68.234:56061: clientconnect
    10.68.68.234:56061: Establish TLS with client
    10.68.68.234:56061: Client Handshake failed. The client may not trust the proxy's certificate for alt3-mtalk.google.com.
    10.68.68.234:56061: ClientHandshakeException('Cannot establish TLS with client (sni: alt3-mtalk.google.com): TlsException("SSL handshake error: Error([(\'SSL routines\', \'ssl3_read_bytes\', \'sslv3 alert certificate unknown\')],)",)',)
    10.68.68.234:56061: clientdisconnect

Add the mitmproxy CA certificate to your phone
----------------------------------------------

You need to tell your phone to trust the mitmproxy CA. To do this, you
can:

-   Point your phone to the URL: <http://mitm.it/> while your VPN
    is active.

-   Or put the mitmproxy-ca-cert.cer file you find in the  /.mitmproxy
    directory:

        ~/.mitmproxy # ls -1
        mitmproxy-ca-cert.cer
        mitmproxy-ca-cert.p12
        mitmproxy-ca-cert.pem
        mitmproxy-ca.pem
        mitmproxy-dhparam.pem

    on some web browser and make your android web browser request that
    URL: you will be prompted to accept the certificate.

Some results
============

At this stage, you should see the decrypted HTTPS traffic going to the
Internet from your phone.

    # mitmdump -T -v 
    Proxy server listening at http://0.0.0.0:8080
    10.68.68.1:57422: clientconnect
    10.68.68.1:57422: serverconnect
      -> 50.19.96.52:443
    10.68.68.1:57422: Establish TLS with server
    10.68.68.1:57422: ALPN selected by server: -
    10.68.68.1:57422: Establish TLS with client
    10.68.68.1:57422: ALPN for client: b'http/1.1'
    10.68.68.1:58819: clientconnect
    10.68.68.1:58819: serverconnect
      -> 50.19.96.52:443
    10.68.68.1:58819: Establish TLS with server
    10.68.68.1:57422: request
      -> Request(GET /spi/v2/platforms/android/apps/com.ninefolders.hd3/settings?icon_hash=4c8a7d21b3cb658d20bae2375aba11c38ca44d9d&display_version=4.0.3&source=4&instance=b5a85ab214d6073aecdc7bb790d4c8a06bc7b1b9&build_version=1400300)
    10.68.68.1:40970: clientconnect
    10.68.68.1:40970: serverconnect
      -> 50.19.96.52:443
    10.68.68.1:58819: ALPN selected by server: -
    10.68.68.1:58819: Establish TLS with client
    10.68.68.1:58819: ALPN for client: b'http/1.1'
    10.68.68.1:57422: response
      -> Response(200 OK, application/json; charset=utf-8, 729b)
    10.68.68.1:57422: GET https://50.19.96.52/spi/v2/platforms/android/apps/com.ninefolders.hd3/settings?icon_hash=4c8a7d21b3cb658d20bae2375aba11c38ca44d9d&display_version=4.0.3&source=4&instance=b5a85ab214d6073aecdc7bb790d4c8a06bc7b1b9&build_version=1400300
                   << 200 OK 729b
    10.68.68.1:40970: Establish TLS with server
    10.68.68.1:43425: clientconnect
    10.68.68.1:43425: serverconnect
      -> 216.58.208.196:443
    10.68.68.1:39545: clientconnect
    10.68.68.1:39545: serverconnect
      -> 216.58.206.238:443
    10.68.68.1:43425: Establish TLS with server
    10.68.68.1:39545: Establish TLS with server
    10.68.68.1:43425: ALPN selected by server: h2
    10.68.68.1:43425: Establish TLS with client
    10.68.68.1:39545: ALPN selected by server: h2
    10.68.68.1:39545: Establish TLS with client
    10.68.68.1:43425: ALPN for client: b'h2'
    10.68.68.1:39545: ALPN for client: b'h2'
    10.68.68.1:40970: ALPN selected by server: -
    10.68.68.1:40970: Establish TLS with client
    10.68.68.1:40970: ALPN for client: b'http/1.1'
    10.68.68.1:58819: request
      -> Request(GET /spi/v2/platforms/android/apps/com.ninefolders.hd3/settings?icon_hash=4c8a7d21b3cb658d20bae2375aba11c38ca44d9d&display_version=4.0.3&source=4&instance=b5a85ab214d6073aecdc7bb790d4c8a06bc7b1b9&build_version=1400300)
    10.68.68.1:58819: response
      -> Response(200 OK, application/json; charset=utf-8, 729b)
    10.68.68.1:58819: GET https://50.19.96.52/spi/v2/platforms/android/apps/com.ninefolders.hd3/settings?icon_hash=4c8a7d21b3cb658d20bae2375aba11c38ca44d9d&display_version=4.0.3&source=4&instance=b5a85ab214d6073aecdc7bb790d4c8a06bc7b1b9&build_version=1400300
                   << 200 OK 729b
    10.68.68.1:40970: request
      -> Request(GET /spi/v2/platforms/android/apps/com.ninefolders.hd3/settings?icon_hash=4c8a7d21b3cb658d20bae2375aba11c38ca44d9d&display_version=4.0.3&source=4&instance=b5a85ab214d6073aecdc7bb790d4c8a06bc7b1b9&build_version=1400300)
    10.68.68.1:40970: response
      -> Response(200 OK, application/json; charset=utf-8, 729b)

The GooglePlay country constraint
=================================

The numbrs mobile application seems to be available only in Germany and
in the UK. I thought that because my mitmproxy was running on a server
in Germany, I would be able to install it, but even after following some
tutorial on the internet, I could not make it work. It seems you now
need a credit card from the country you want to test and I did not have
a German nor a UK credit card.

Conclusion
==========

In this article we presented a method to look at the SSL traffic coming
to/from and Android phone. This method requires very few modification on
the mobile phone side. Because of country restrictions, I was not able
to test the Centralway Numbrs mobile app, however with the method
presented, it would be easy to have a good understanding of the API
entry points used. Note that mitmproxy can be used to get the full
payload of the packets and also to modify the data.

<span>**Appendix**</span>

Netfilter Hooks {#netfilter}
===============

There are five netfilter hooks that programs can register
with@castro2003@ellingwood2015. As packets progress through the stack,
they will trigger the kernel modules that have registered with these
hooks. The hooks that a packet will trigger depends on whether the
packet is incoming or outgoing, the packet’s destination, and whether
the packet was dropped or rejected at a previous point.

The following hooks represent various well-defined points in the
networking stack:

-   NF\_IP\_PRE\_ROUTING: This hook will be triggered by any incoming
    traffic very soon after entering the network stack. This hook is
    processed before any routing decisions have been made regarding
    where to send the packet.

-   NF\_IP\_LOCAL\_IN: This hook is triggered after an incoming packet
    has been routed if the packet is destined for the local system.

-   NF\_IP\_FORWARD: This hook is triggered after an incoming packet has
    been routed if the packet is to be forwarded to another host.

-   NF\_IP\_LOCAL\_OUT: This hook is triggered by any locally created
    outbound traffic as soon it hits the network stack.

-   NF\_IP\_POST\_ROUTING: This hook is triggered by any outgoing or
    forwarded traffic after routing has taken place and just before
    being put out on the wire.

<span>99</span>

Version 1.2 <https://tools.ietf.org/html/rfc5246>

Stuart at root9.net Sunday, 11 November 2012 <span>*SSL Decryption with
Wireshark (Private key and Pre-Master secret)*</span>
<http://www.root9.net/2012/11/ssl-decryption-with-wireshark-private.html>

Android issue 37068375 <span>*Can’t update a wireless network that my
app didn’t create. No permission available to request the acceptance to
the user.*</span> <https://issuetracker.google.com/issues/37068375>

Proxy Settings
<https://play.google.com/store/apps/details?id=com.lechucksoftware.proxy.proxysettings>

<http://docs.mitmproxy.org/en/stable/howmitmproxy.html>

<http://docs.mitmproxy.org/en/stable/install.html>

chmod000 <span>*Guide to Android SSL sniffing on Linux*</span> August 6,
2016
<https://forum.level1techs.com/t/guide-to-android-ssl-sniffing-on-linux/106261>

Philipp C. Heckel <span>*How To: Use mitmproxy to read and modify HTTPS
traffic*</span> July 1, 2013
<https://blog.heckel.xyz/2013/07/01/how-to-use-mitmproxy-to-read-and-modify-https-traffic-of-your-phone/#Install-mitmproxy-CA-certificate-in-the-phone>

Justin Ellingwood August 20, 2015 <span>*A Deep Dive into Iptables and
Netfilter Architecture*</span>
<https://www.digitalocean.com/community/tutorials/a-deep-dive-into-iptables-and-netfilter-architecture>

Victor Castro <span>*Roll Your Own Firewall with Netfilter*</span> Oct
13, 2003 <http://www.linuxjournal.com/article/7184>
