---
date: '2018-08-06T03:10:00.001-0700'
tags: linux, lua, openresty, nginx
---

For introduction to lua:

http://tylerneylon.com/a/learn-lua/


https://yos.io/2016/01/28/building-an-api-gateway-with-lua-and-nginx/
http://leafo.net/posts/creating_an_image_server.html

http://www.staticshin.com/programming/definitely-an-open-resty-guide/


https://youtu.be/nlt4XKhucS4

https://youtu.be/OUUiS28hZuw

https://youtu.be/wdRGOE1N-FA

https://youtu.be/LvpDE5z2_XE


https://openresty.org/en/linux-packages.html

```
sudo apt-get install openresty
```


```
root@hp:~# netstat -nap | grep 80
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      23860/nginx: master 
```



```
ls -1 /usr/local/openresty 
bin
luajit
lualib
nginx
openssl
pcre
site
zlib
```


```
root     23860  0.0  0.0  41116   992 ?        Ss   19:58   0:00 nginx: master process /usr/local/openresty/nginx/sbin/nginx -g daemon on; master_process on;
```



```
root@hp:/etc/systemd# systemctl status openresty
● openresty.service - full-fledged web platform
   Loaded: loaded (/lib/systemd/system/openresty.service; enabled; vendor preset: enabled)
   Active: active (running) since Mon 2018-08-06 19:58:18 CEST; 9min ago
  Process: 23859 ExecStart=/usr/local/openresty/nginx/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
  Process: 23856 ExecStartPre=/usr/local/openresty/nginx/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
 Main PID: 23860 (nginx)
    Tasks: 2 (limit: 4915)
   CGroup: /system.slice/openresty.service
           ├─23860 nginx: master process /usr/local/openresty/nginx/sbin/nginx -g daemon on; master_process on;
           └─23861 nginx: worker process

Aug 06 19:58:18 hp systemd[1]: Starting full-fledged web platform...
Aug 06 19:58:18 hp systemd[1]: Started full-fledged web platform.
```



https://www.digitalocean.com/community/tutorials/how-to-use-the-openresty-web-framework-for-nginx-on-ubuntu-16-04


kong
https://github.com/Kong/kong
https://konghq.com/install/

https://github.com/Kong/kong/blob/master/t/01-pdk/02-log/03-set_format.t
use Test::Nginx::Socket::Lua;

https://github.com/openresty/test-nginx

https://openresty.gitbooks.io/programming-openresty/content/testing/preparing-tests.html




https://blog.cloudflare.com/cloudflares-new-waf-compiling-to-lua/
