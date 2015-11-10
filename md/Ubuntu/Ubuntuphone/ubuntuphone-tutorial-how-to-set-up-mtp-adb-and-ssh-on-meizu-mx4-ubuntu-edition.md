---
file: ubuntuphone-tutorial-how-to-set-up-mtp-adb-and-ssh-on-meizu-mx4-ubuntu-edition.md
title: "Ubuntuphone - Tutorial : How to set up mtp, adb and ssh on Meizu MX4 Ubuntu Edition"
description: "Ubuntuphone Tricks"
date: 2015-07-07
author: Winael
corrections: KennedyM
category: Ubuntu
language: EN
tags: Ubuntu,Ubuntuphone,Meizu,MX4,adb,mtp,ssh
viewport: 'width=device-width, initial-scale=1'
---

<meta http-equiv='Content-Type' content='text/html; charset=utf-8' />


<!-- FR
L'un des principaux avantages des Ubuntuphones, c'est de pouvoir facilement prendre la main dessus au travers du protocole abd, voir d'initier des sessions SSH facilement dessus. Malheureusement, le Meizu MX4 Ubuntu Edition se montre quelque peu réticent. Heureusement le 'fix' prends moins de temps à mettre en place qu'une pub de TF1.
-->

<!-- lang: EN -->
One of the major benefits of Ubuntu Phones is the facility to easily take control of it through the abd protocol, or easily initiate SSH sessions into it. Unfortunately, the Meizu MX4 Ubuntu Edition is somewhat 'reluctant'! Fortunately, the 'fix' takes less time to set up than a TV ad.

<!-- lang: FR
# Pré-requis
-->

<!-- lang: EN -->
# Requirements

<!-- lang: FR
Nous allons commencer par installer tous les éléments qui nous seront utiles pour ce tutoriel :
-->

<!-- EN-->
We'll begin by installing all the necessary elements for this tutorial:

<!-- Codeblock, do not translate -->
```sh
$ sudo add-apt-repository ppa:ubuntu-sdk-team/ppa
$ sudo add-apt-repository ppa:phablet-team/tools
$ sudo apt-get update
$ sudo apt-get dist-upgrade
$ sudo apt-get install libmtp-common mtp-tools libmtp-dev libmtp-runtime libmtp9 ubuntu-sdk phablet-tools
```

<!-- lang: FR
Puis nous allons activer le mode debug sur le téléphone. Sur le téléphone se rendre sur :
-->

<!-- EN -->
Then we have to activate the debug mode on the phone. Go to:

<!-- lang: FR
``Paramètre Système`` &#8594; ``A propos de ce téléphone``  &#8594; ``Mode développeur``  
-->

<!-- lang: EN -->
``System settings`` &#8594; ``About this phone`` &#8594; ``Developer Mode``

<!-- lang: FR
et activer le mode developpeur.
-->

<!-- lang: EN -->
and activate the developer mode.

![Go to panel settings][1]
![Go to About the phone][2]
![Go to dev mode][3]
![Activate dev mode][4]

<!-- lang: FR
# Paramétrage du MTP
-->

<!-- lang: EN -->
# Setting up the MTP:

<!-- lang: FR
Tout d'abord, nous sommes de nombreux Insiders a avoir constaté que le téléphone de Meizu était mal reconnu par notre OS favoris. Impossible de monter le téléphone en Mass Storage, donc d'y transférer des fichiers par USB, dont nos clés SSH, ni même de le piloter via adb.
-->

<!-- lang: EN -->
First, as Insiders, we have found that the Meizu phone was poorly recognized by our favorite OS. We were unable to mount the phone in mass storage mode, and so it's impossible to transfer files into it via USB using our SSH keys, or control it via adb.

<!-- lang: FR
Dans ce cas, la première des choses à faire est d'interroger lsusb
-->

<!-- lang: EN -->
In this case, the first thing to do is to interrogate ``lsusb``:

<!-- lang: FR
Téléphone non branché :
-->

<!-- lang: EN -->
With an unconnected phone:

<!-- Codeblock, do not translate -->
```sh
$ lsusb  
Bus 002 Device 003: ID 058f:6364 Alcor Micro Corp. AU6477 Card Reader Controller  
Bus 002 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub  
Bus 002 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub  
Bus 006 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub  
Bus 005 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub  
Bus 001 Device 005: ID 046d:c00c Logitech, Inc. Optical Wheel Mouse  
Bus 001 Device 004: ID 046d:c31d Logitech, Inc. Media Keyboard K200  
Bus 001 Device 003: ID 046d:0825 Logitech, Inc. Webcam C270  
Bus 001 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub  
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub  
Bus 004 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub  
Bus 003 Device 002: ID 03f0:8711 Hewlett-Packard Deskjet 2050 J510  
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
```

<!-- lang: FR
Téléphone branché :
-->

<!-- lang: EN -->
With a connected phone:

<!-- Codeblock, do not translate -->
```sh
$ lsusb
Bus 002 Device 003: ID 058f:6364 Alcor Micro Corp. AU6477 Card Reader Controller
Bus 002 Device 004: ID 2a45:0c02 
Bus 002 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 002 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 006 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 005 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 001 Device 005: ID 046d:c00c Logitech, Inc. Optical Wheel Mouse
Bus 001 Device 004: ID 046d:c31d Logitech, Inc. Media Keyboard K200
Bus 001 Device 003: ID 046d:0825 Logitech, Inc. Webcam C270
Bus 001 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 004 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 003 Device 002: ID 03f0:8711 Hewlett-Packard Deskjet 2050 J510
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
```

<!-- lang: FR
On peut raisonnablement penser que la ligne Bus 002 Device 004: ID 2a45:0c02 corresponde à notre appareil.
-->

<!-- lang: EN -->
It is reasonable to think that the line ``Bus 002 Device 004: ID 2a45: 0c02`` matches our device.

<!-- lang: FR
Mettons de côté de l'ID du fabricant et ID du modèle respectivement dans les variables ``VENDORID`` et ``MODELID``:
-->

<!-- lang: EN -->
Let's save the manufacturer's ID and Model ID in the variables ``VENDORID`` and ``MODELID`` respectively:

<!-- Codeblock, do not translate -->
```sh
$ export VENDORID="2a45"
$ export MODELID="0c02"
```

<!-- lang: FR
FUSE peut permettre à un autre utilisateur que root de monter un système de fichier tiers. Pour cela il faut décommenter la ligne ``user_allow_other`` dans le fichier ``/etc/fuse.conf`` :
-->

<!-- lang: EN -->
FUSE can permit another user as root, to mount a third party filesystem. This requires that we uncomment the line ``user_allow_other`` in the file ``/etc/fuse.conf``:

<!-- Codeblock, do not translate -->
```sh
$ sudo sed -i 's/#user_allow_other/user_allow_other/' /etc/fuse.conf
```

<!-- lang: FR
Ensuite, nous devons modifier les règle udev en charge du MTP qui se trouvent dans le fichier ``/lib/udev/rules.d/69-libmtp.rules`` pour y déclarer le Meizu :
-->

<!-- lang: EN -->
Then we have to change the udev rules that support MTP in the file ``/lib/udev/rules.d/ 69-libmtp.rules`` order to declare the Meizu:

<!-- Codeblock, do not translate -->
```sh
$ sudo bash -c 'cat << EOF >> /etc/udev/rules.d/69-libmtp.rules
# Meizu MX4
ATTR{idVendor}=="2a45", ATTR{idProduct}=="0c02", SYMLINK+="MeizuMX4Ubuntu", ENV{ID_MTP_DEVICE}="1", ENV{ID_MEDIA_PLAYER}="1"
EOF'
```

<!-- lang: FR
Normalement, en branchant votre Meizu MX 4 Ubuntu Edition, vous devriez le voir monté automatiquement.
-->

<!-- lang: EN -->
Normally, by plugging in your Meizu MX4 Ubuntu Edition, you should see it mounted automatically.

<!-- lang: FR
# Configuration d'adb
-->

<!-- lang: EN -->
# Setting up ``adb``:

<!-- lang: FR
Il est possible de piloter le Meizu MX4 Ubuntu Edition via adb (Android Debug Bridge). Pour le configurer, il suffit d'ajouter l'idVendor dans le fichier $HOME/.android/adb_usb.ini.
-->

<!-- lang: EN -->
It's possible to control the Meizu MX4 Ubuntu Edition through ``adb`` (Android Debug Bridge). To set it up, you just have to add the ``idVendor`` in the file ``$HOME/.android/adb_usb.ini``:

<!-- Codeblock, do not translate -->
```sh
$ mkdir $HOME/.android
$ echo "0x2a45" &gt;&gt; $HOME/.android/adb_usb.ini
```

<!-- lang: FR
Puis on redemarre le service adb :
-->

<!-- lang: EN -->
Then we restart the ``adb`` service:

<!-- Codeblock, do not translate -->
```sh
$ adb kill-server
```

<!-- lang: FR
Le téléphone Meizu MX4 Ubuntu Edition est maintenant reconnu lorsque l'on tape la commande :
-->

<!-- lang: EN -->
The phone Meizu MX4 Ubuntu Edition is now recognized when we run the command:

<!-- Codeblock, do not translate -->
```sh
$ adb devices
* daemon not running. starting it now on port 5037 *
* daemon started successfully *
List of devices attached 
75HACL66VJ8X    device
```

<!-- lang: FR
Pour accéder au téléphone, il suffit de taper :
-->

<!-- lang: EN -->
To access your device, you just run:

<!-- Codeblock, do not translate -->
```sh
$ adb shell
phablet@ubuntu-phablet:~$
```

<!-- lang: FR
# Configuration de SSH
-->

<!-- lang: EN -->
# Setting up SSH:

<!-- lang: FR
Pouvoir monter son téléphone comme une unité de stockage amovible, c'est bien.
Pouvoir piloter son téléphone en ligne de commande, c'est mieux.
Mais ce qui serait top c'est de pouvoir le faire sans fil, sans avoir à sortir le téléphone de sa poche. Et bien c'est possible de le faire, grâce au WiFi au travers de son réseau local.
-->

<!-- lang: EN -->
Being able to manage our phone using the command-line is better.
But the best – can we control it wirelessly?
Well, it is possible, thanks to WiFi through our local network.

<!-- lang: FR
## L'échange de clés
-->

<!-- lang: EN -->
## Keys exchange:

<!-- lang: FR
Afin de sécuriser la connexion en ligne de commande entre les appareils mobiles tournant sur Ubuntu et les postes de travail, il est conseillé d'utliser phablet-shell, la commande issue des phablet-tools permettant de mettre en place une connexion SSH entre les appareils. Au premier lancement, phablet-shell va gérer l'échange de clé, puis se connecter en SSH sur l'appareil mobile
-->

<!-- lang: EN -->
To secure the connection from the command-line between mobile devices running workstations Ubuntu, it is recommended to use ``phablet-shell``, one of the tools that come from ``phablet-tools`` that can establish a SSH connection between devices. During the first launch, ``phablet-shell`` will handle the keys exchange, then connect via SSH on the mobile device 

<!-- Codeblock, do not translate -->
```sh
$ phablet-shell 
/home/winael/.ssh/known_hosts updated.
Original contents retained as /home/winael/.ssh/known_hosts.old
Warning: Permanently added '[localhost]:2222' (RSA) to the list of known hosts.
Welcome to Ubuntu 15.04 (GNU/Linux 3.10.35+ armv7l)

 * Documentation:  https://help.ubuntu.com/
Last login: Sun Jun 28 14:44:03 2015 from localhost.localdomain
phablet@ubuntu-phablet:~$
```

<!-- lang: FR
## Fixation de l'adresse IP
-->

<!-- lang: EN -->
## Fixing IP adress

<!-- lang: EN -->
Now, it is recommanded to fix the IP Address to always use the same address on a specific network.

<!-- lang: FR
Depuis l'appareil mobile Meizu MX4 Ubuntu Edition on liste l'IP courante pour le téléphone
-->

<!-- lang: EN -->
From the Meizu MX4 Ubuntu Edition mobile device, we list all the current IPs for the phone:

<!-- Codeblock, do not translate -->
```sh
$ sudo -i
[sudo] password for phablet: 
# ip addr show wlan0
11: wlan0:  mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 38:bc:1a:1f:7e:b4 brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.23/24 brd 192.168.1.255 scope global dynamic wlan0
       valid_lft 82074sec preferred_lft 82074sec
    inet6 fe80::3abc:1aff:fe1f:7eb4/64 scope link 
       valid_lft forever preferred_lft forever
```

<!-- lang: FR
On se rend dans le répertoire ``/etc/NetworkManager`` et on regarde le contenu du paramétrage de sa connexion :
-->

<!-- lang: EN -->
We must go to the ``/etc/NetworkManager`` directory and take a look at the content of our connection settings:

<!-- Codeblock, do not translate -->
```sh
# cd /etc/NetworkManager/system-connections
# ls
# cat 
```

<!-- lang: FR
On édite ensuite la connexion :
-->

<!-- lang: EN -->
We edit the connection:

<!-- lang: FR
- On affiche d'abord la liste des connexions paramétrées
-->

<!-- lang: EN -->
First, we list all the connections setup:

<!-- Codeblock, do not translate -->
```sh
# nmcli connection show
NAME                       UUID                                  TYPE             DEVICE 
Livebox-Navijobard         0c0a0040-ee0b-494c-a297-c5bfc2c1133c  802-11-wireless  wlan0  
AndroidAP                  830dbbc7-8b8e-42be-a41c-9584988731b1  802-11-wireless  --     
NUMA Welcome               aafc220a-c594-44a4-9095-483fccddbbc6  802-11-wireless  --     
Nexus 5 Network            b7801b53-637f-4dde-a250-3479184ab3d7  bluetooth        --     
/208150004998871/context1  9e611658-b475-7c4e-954b-edc06b75ab87  gsm              ril_0  
NUMA Inside                baf064d2-588c-40aa-a291-1efb8779ec3a  802-11-wireless  --     
```

<!-- lang: FR
- On édite la connexion qui nous interesse
-->

<!-- lang: EN -->
- We edit the connections that interesterd us

<!-- Codeblock, do not translate -->
```sh
# nmcli connection edit Livebox-Navijobard

===| nmcli interactive connection editor |===

Editing existing '802-11-wireless' connection: 'Livebox-Navijobard'

Type 'help' or '?' for available commands.
Type 'describe [.]' for detailed property description.

You may edit the following settings: connection, 802-11-wireless (wifi), 802-11-wireless-security (wifi-sec), 802-1x, ipv4, ipv6
```

<!-- lang: FR
- On affiche la configuration actuelle
-->

<!-- lang: EN -->
- We print the actual configuration:

<!-- Codeblock, do not translate -->
```sh 
nmcli> print
===============================================================================
                Connection profile details (Livebox-Navijobard)
===============================================================================
connection.id:                          Livebox-Navijobard
connection.uuid:                        0c0a0040-ee0b-494c-a297-c5bfc2c1133c
connection.interface-name:              --
connection.type:                        802-11-wireless
connection.autoconnect:                 yes
connection.timestamp:                   1436215756
connection.read-only:                   no
connection.permissions:                 
connection.zone:                        --
connection.master:                      --
connection.slave-type:                  --
connection.secondaries:                 
connection.gateway-ping-timeout:        0
-------------------------------------------------------------------------------
802-11-wireless.ssid:                   Livebox-Navijobard
802-11-wireless.mode:                   infrastructure
802-11-wireless.band:                   --
802-11-wireless.channel:                0
802-11-wireless.bssid:                  --
802-11-wireless.rate:                   0
802-11-wireless.tx-power:               0
802-11-wireless.mac-address:            49:AB:3D:5G:6E:D4
802-11-wireless.cloned-mac-address:     --
802-11-wireless.mac-address-blacklist:  
802-11-wireless.mtu:                    auto
802-11-wireless.seen-bssids:            7B:04:E7:AC:8A:FE,7B:04:E7:AC:8A:FF
802-11-wireless.hidden:                 no
802-11-wireless.powersave:              --
-------------------------------------------------------------------------------
802-11-wireless-security.key-mgmt:      wpa-psk
802-11-wireless-security.wep-tx-keyidx: 0
802-11-wireless-security.auth-alg:      open
802-11-wireless-security.proto:         
802-11-wireless-security.pairwise:      
802-11-wireless-security.group:         
802-11-wireless-security.leap-username: --
802-11-wireless-security.wep-key0:      --
802-11-wireless-security.wep-key1:      --
802-11-wireless-security.wep-key2:      --
802-11-wireless-security.wep-key3:      --
802-11-wireless-security.wep-key-flags: 0 (none)
802-11-wireless-security.wep-key-type:  0 (unknown)
802-11-wireless-security.psk:           --
802-11-wireless-security.psk-flags:     0 (none)
802-11-wireless-security.leap-password: --
802-11-wireless-security.leap-password-flags:0 (none)
-------------------------------------------------------------------------------
ipv4.method:                            auto
ipv4.dns:                               
ipv4.dns-search:                        
ipv4.addresses:                         
ipv4.routes:                            
ipv4.ignore-auto-routes:                no
ipv4.ignore-auto-dns:                   no
ipv4.dhcp-client-id:                    --
ipv4.dhcp-send-hostname:                yes
ipv4.dhcp-hostname:                     --
ipv4.never-default:                     no
ipv4.may-fail:                          yes
-------------------------------------------------------------------------------
ipv6.method:                            auto
ipv6.dns:                               
ipv6.dns-search:                        
ipv6.addresses:                         
ipv6.routes:                            
ipv6.ignore-auto-routes:                no
ipv6.ignore-auto-dns:                   no
ipv6.never-default:                     no
ipv6.may-fail:                          yes
ipv6.ip6-privacy:                       -1 (unknown)
ipv6.dhcp-hostname:                     --
-------------------------------------------------------------------------------
```

<!-- lang: FR
- On se rend dans la configuration ipv4
-->

<!-- lang: EN -->
- We have to set the IPv4 configuration:

<!-- Codeblock, do not translate -->
```sh
nmcli> goto ipv4
You may edit the following properties: method, dns, dns-search, addresses, address-labels, routes, ignore-auto-routes, ignore-auto-dns, dhcp-client-id, dhcp-send-hostname, dhcp-hostname, never-default, may-fail
```

<!-- lang: FR
- On passe la configuration IPv4 en manuelle
-->

<!-- lang: EN -->
- We switch the IPv4 configuration to manual:

<!-- Codeblock, do not translate -->
```sh
nmcli ipv4> set method manual
```

<!-- lang: FR
On modifie l'adresse IP, le masque et la passerelle
-->

<!-- lang: EN -->
- We modify the IP address, the mask, and the gateway:

<!-- Codeblock, do not translate -->
```sh
nmcli ipv4> set addresses 192.168.1.101/24 192.168.1.255
```

<!-- lang: FR
On modifie l'adresse DNS
-->

<!-- lang: EN -->
- We modify the DNS address:

<!-- Codeblock, do not translate -->
```sh
nmcli ipv4> set dns 8.8.8.8 8.8.4.4
```

<!-- lang: FR
On sort de la configuration de l'IPv4
-->

<!-- lang: EN -->

- We exit from the IPv4 configuration:

<!-- Codeblock, do not translate -->
```sh
nmcli ipv4> back
```

<!-- lang: FR
On active la connexion automatique
-->

<!-- lang: EN -->
- We activate the automatic connection:

<!-- Codeblock, do not translate -->
```sh
nmcli> set connection.autoconnect TRUE
```

<!-- lang: FR
On affiche la nouvelle configuration
-->

<!-- lang: EN -->
- We print the new settings:

<!-- Codeblock, do not translate -->
```sh
nmcli> print
```

<!-- lang: FR
On sauvegarde et on quitte
-->

<!-- lang: EN -->
- - Save, and exit:

<!-- Codeblock, do not translate -->
```sh
nmcli> save
nmcli> quit
```

<!-- lang: FR
On redemarre le téléphone puis on regarde son adresse ip
-->

<!-- lang: EN -->
We reboot the phone and take a look on its IP:

<!-- Codeblock, do not translate -->
```sh
phablet@ubuntu-phablet:~$ ifconfig
ccmni0    Link encap:Ethernet  HWaddr fe:3f:26:a0:08:56  
          inet addr:10.163.45.115  Mask:255.255.255.0
          UP RUNNING NOARP  MTU:1500  Metric:1
          RX packets:134 errors:0 dropped:0 overruns:0 frame:0
          TX packets:140 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:33299 (33.2 KB)  TX bytes:11014 (11.0 KB)

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:492 errors:0 dropped:0 overruns:0 frame:0
          TX packets:492 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0 
          RX bytes:45396 (45.3 KB)  TX bytes:45396 (45.3 KB)

wlan0     Link encap:Ethernet  HWaddr 38:bc:1a:1f:7e:b4  
          inet addr:192.168.1.101  Bcast:192.168.1.255  Mask:255.255.255.0
          inet6 addr: fe80::3abc:1aff:fe1f:7eb4/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:8 errors:0 dropped:0 overruns:0 frame:0
          TX packets:8 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:718 (718.0 B)  TX bytes:692 (692.0 B)
```

<!-- lang: FR
L'adresse IP est bien paramétrée avec l'adresse que nous avons fixée
Il ne nous reste plus qu'à paramétrer le serveur DNS de notre box internet ou dans le fichier /etc/hosts
Ensuite nous pouvons faire :
-->

<!-- lang: EN -->

The IP address is set up with the address that we fixed.

Now, we have just to set up the DNS resolution of our Internet box in the file ``/etc/hosts`

Then we can just connect to the phone with the command:

<!-- Codeblock, do not translate -->
```sh
$ ssh phablet@mx4ubuntu
```

<!-- lang: FR
pour vous connecter en ligne de commande ou ajouter un signet vers sftp://phablet@mx4ubuntu:/home/phablet dansnautilus pour "monter" votre téléphone grâce au WiFi et vous simplifier la vie pour les transferts de fichiers
A bientôt pour d'autres astuces !!!
-->

<!-- lang: EN -->
You can add a bookmark to ``sftp://phablet@mx4ubuntu:/home/phablet`` in ``nautilus`` to mount your phone using WiFi. It will simplify your life for file transfers.

See you soon for more tips!!!

Thx KennedyM for the corrections :)

[1]: http://2.bp.blogspot.com/-nEhpcaF9gQQ/VjNfOCkYTXI/AAAAAAAA9gY/SaMZQJ74PxA/s320/screenshot20150705_011856396.png
[2]: http://2.bp.blogspot.com/-4jLiHztMuXc/VjNfOHmYJoI/AAAAAAAA9gc/-f10RfzONno/s320/screenshot20150705_012125728.png
[3]: http://1.bp.blogspot.com/-1fXQXI_PlgY/VjNfODd8uGI/AAAAAAAA9gU/bN-NXbVgd9s/s320/screenshot20150705_012140996.png
[4]: http://1.bp.blogspot.com/-6DUQ7uA4fpo/VjNfPCFSbOI/AAAAAAAA9gg/ow7YtAuLo_4/s1600/screenshot20150705_012147771.png
