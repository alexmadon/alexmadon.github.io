huawei b715 prixtel

madon@hp:~/finopslib$ /sbin/route -n
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
0.0.0.0         192.168.1.1     0.0.0.0         UG    100    0        0 enp0s31f6
10.10.0.1       10.10.0.69      255.255.255.255 UGH   0      0        0 psh-vpn
10.10.0.69      0.0.0.0         255.255.255.255 UH    0      0        0 psh-vpn
169.254.0.0     0.0.0.0         255.255.0.0     U     1000   0        0 enp0s31f6
172.17.0.0      0.0.0.0         255.255.0.0     U     0      0        0 docker0
192.168.1.0     0.0.0.0         255.255.255.0   U     100    0        0 enp0s31f6
ma



The default password for this DNA Kotimokkula B715 is 1234. However please check this from a sticker behind the back cover of the device (indicated after "asetussivun salasana"). If you have changed the password yourself, you can revert B715 to factory settings by pressing "reset" button for 30 seconds. Please keep in mind pushing "reset" button under 30 seconds will result only a reboot. Reset will turn all settings to their default.

PIN: 0000
passwd default: 1234


DNA-Mokkula-2G-1G31QB
passwd: see back of router


21101
	
MMS message. Message type not supported by your router
03:32:09
 
PRIXTEL
	
Bonjour, bienvenue chez PRIXTEL. Votre répondeur est le 789. Merci d'avoir choisi PRIXTEL.


http://192.168.1.1/html/content.html#mobileconnection




https://assistance.prixtel.com/questions/900239-configurer-internet-mms-smartphone 
Configurer manuellement les APN Orange Internet et MMS sur un téléphone Android

 

Si vous utilisez un smartphone Android sur le réseau Orange, voici les deux points d'accès à créer : 

-APN INTERNET-

Nom : Orange World
APN : orange
Nom d'utilisateur : orange
Mot de passe : orange
MCC : 208
MNC : 01
Type d'authentification : PAP

Type d'APN : default,supl

Les autres champs restent vides ou avec les valeurs par défaut.

Enregistrez cet APN.






-APN MMS-

Nom : Orange MMS
APN : orange.acte
Nom d'utilisateur : orange
Mot de passe  : orange
MMSC : http://mms.orange.fr
Proxy MMS : 192.168.10.200
Port MMS : 8080
MCC : 208
MNC : 01

Type d'authentification : PAP

Type d'APN : mms

Les autres champs restent vides ou avec les valeurs par défaut.

Enregistrez cet APN puis éteignez et rallumez votre téléphone.

N'oubliez pas de vérifier que les données mobiles sont bien activées et que vous avez sélectionné au moins le réseau 2G/3G dans les Préférences réseau (ou Mode réseau). Ensuite, désactivez le Wifi puis ouvrez votre navigateur web pour voir si Internet fonctionne et testez l'envoi et la réception de MMS.
