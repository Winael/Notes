---
file: ubuntu-convergence-part-1-setting-it-up.md
title:  "Ubuntu convergence, part 1: Setting it up"
author: Sturm Flut
translation: Winael
date:   2015-11-01 20:00:00
categories: Ubuntu
tags: Ubuntu, phone, tablet, Ubuntutouch, convergence, desktop
status: translation_WIP
---

<!-- Chapeau -->

**Je vous propose aujourd'hui la traduction d'un article de Sturm Flut, contributeur Ubuntu allemand. Ce premier artcle d'une série vous propose de mettre en place votre environnement convergent Ubuntu. Bonne lecture !**

----------

# Ubuntu Convergence, partie 1 : Mise en place

<!-- lang: EN
<div lang="english">
Now that Ubucon Germany 2015 and UbuContest 2015 are over, I've finally found some time to blog about technical things again. And hooray: We have Convergence! You can now actually connect a phone to an external display, pair keyboard and mouse and get a desktop experience! In this article I will show in detail how I set everything up.
</div>
-->

<!-- lang: FR -->
<div lang="french">
Maintenant que l'Ubucon Allemagne 2015 et l'UbuContest 2015 sont terminés, j'ai enfin trouvé un peu de temps pour bloguer à nouveau à propos de choses techniques. Et hourra : Nous avons la Convergence ! Vous pouvez maintenant effectivement connecter un téléphone à un écran externe, y coupler un clavier et une souris et obtenir une expérience de bureau ! Dans cet article je vais vous montrer en détail comment j'ai tout mis en place.
</div>

![Workbench desk with Convergence setup](https://sturmflut.github.io//images/ubuntu-convergence-part-1/desk.jpg)

<!-- lang: EN
<div lang="english">
My good old "workbench" desk at home. At the left the Nexus 4 connected to Bluetooth keyboard/mouse and an external 24" display, at the right my Dell Latitude E7450 with conventional USB keyboard and mouse. Note the not-quite-Ubuntu-colory LED light in the background.
</div>
-->

<!-- lang: FR -->
<div lang="french">
Mon bon vieux bureau « plan de travail »  à la maison. A gauche le Nexus 4 connecté en Bluetooth au clavier et la souris et branché sur un écran externe 24", et à droite mon Dell Latitude E7450 avec un clavier USB et une souris classique. Notez le colorie pas-vraiment-Ubuntu de la lumière LED en arrière-plan.
</div>

<!-- lang: EN
<div lang="english">
## Necessary hard- and software
</div>
-->

<!-- lang: FR -->
<div lang="french">
## Matériel et logiciels nécessaires
</div>

<!-- lang: EN
I am using the following parts:

* Nexus 4 16 GB

* SlimPort to HDMI adapter, with Micro-USB plug for simultaneous power supply

* Logitech K380 Bluetooth keyboard

* Logitech M557 Optical Bluetooth mouse
-->

<!-- lang: FR -->
J'utilise les élements suivants :

* 1 Smartphone Google Nexus 4 16Go
* 1 Adaptateur Slimport to HDMI, avec Micro-USB pour alimenter simultanément le smartphone
* 1 Clavier Bluetooth Logitech K380
* 1 Souris Bluetooth Optique Logitech M557

The most important convergence bits landed with image r273 of the `ubuntu-touch/rc-proposed/ubuntu` channel. At the time of writing my phone is running image r276 of the same channel.

**NOTE**: I haven't had much luck with anything else than SlimPort to HDMI, especially not when trying to convert the HDMI signal to something else using a second adapter (e.g. Slimport to HDMI and then HDMI to DVI). If you're going to demo Convergence somewhere, make sure the display/projector has HDMI and works with your phone.


## Setting it up

The first step is to test if the SlimPort-to-HDMI adapter works. Hotplugging the external display is quite unreliable and will very often result in the external display only showing half of the picture, as can be seen in the following image:

![Hotplug problems]({{site.url}}/images/ubuntu-convergence-part-1/hotplug.jpg)

So turn off your phone, connect the adapter to the external display and boot the phone:

![External display has been detected and is being used]({{site.url}}/images/ubuntu-convergence-part-1/external-connected.jpg)

![The lockscreen is still the one from the phone UI]({{site.url}}/images/ubuntu-convergence-part-1/external-phone-lockscreen.jpg)

Now we know everything works fine and the phone drives the external display correctly. The phone will currently switch to desktop mode as soon as a mouse is connected, but your USB port is already occupied by the SlimPort adapter and the port cannot do SlimPort and USB data at the same time. So you really need a Bluetooth mouse and keyboard.


## Set up the Bluetooth devices

Because the phone touchscreen can no longer be used when an external display is connected, you have to disconnect the phone again, pair the Bluetooth devices and then connect the external display again. This process is straightforward:

![Connecting Bluetooth devices]({{site.url}}/images/ubuntu-convergence-part-1/bluetooth1.jpg)

![Bluetooth device details]({{site.url}}/images/ubuntu-convergence-part-1/bluetooth2.jpg)


## Finally: Desktop Mode

You will have noticed that the phone immediately switched its internal display to desktop mode when the Bluetooth mouse was successfully paired:

![Desktop mode on the internal display]({{site.url}}/images/ubuntu-convergence-part-1/desktop-mode-internal.jpg)

This is not really useful, so connect the external display again to enjoy full desktop mode :

![Desktop mode on the external display]({{site.url}}/images/ubuntu-convergence-part-1/desktop-mode-external.jpg)

This, ladies and gentleman, is Convergence. Still lots of things missing, but we will take care about that in the next part of this series.

