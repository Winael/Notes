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
<span lang="english">
    Now that Ubucon Germany 2015 and UbuContest 2015 are over, I've finally found some time to blog about technical things again. And hooray: We have Convergence! You can now actually connect a phone to an external display, pair keyboard and mouse and get a desktop experience! In this article I will show in detail how I set everything up.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Maintenant que l'Ubucon Allemagne 2015 et l'UbuContest 2015 sont terminés, j'ai enfin trouvé un peu de temps pour bloguer à nouveau à propos de choses techniques. Et hourra : Nous avons la Convergence ! Vous pouvez maintenant effectivement connecter un téléphone à un écran externe, y coupler un clavier et une souris et obtenir une expérience de bureau ! Dans cet article je vais vous montrer en détail comment j'ai tout mis en place.
</span>

<!-- lang: EN
<span lang="english">
    ![Workbench desk with Convergence setup][1]
</span>
-->

<!-- lang: FR -->
<span lang="french">
![Plan de travail de bureau avec Convergence paramétrée][1]
</span>

<!-- lang: EN
<span lang="english">
    My good old "workbench" desk at home. At the left the Nexus 4 connected to Bluetooth keyboard/mouse and an external 24" display, at the right my Dell Latitude E7450 with conventional USB keyboard and mouse. Note the not-quite-Ubuntu-colory LED light in the background.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Mon bon vieux bureau « plan de travail »  à la maison. A gauche le Nexus 4 connecté en Bluetooth au clavier et la souris et branché sur un écran externe 24", et à droite mon Dell Latitude E7450 avec un clavier USB et une souris classique. Notez le colorie pas-vraiment-Ubuntu de la lumière LED en arrière-plan.
</span>

<!-- lang: EN
## <span lang="english">Necessary hard- and software</span>
-->

<!-- lang: FR -->
## <span lang="french">Matériel et logiciels nécessaires</span>

<!-- lang: EN
<span lang="english">
    I am using the following parts:
    
    - Nexus 4 16 GB
    
    - SlimPort to HDMI adapter, with Micro-USB plug for simultaneous power supply
    
    * Logitech K380 Bluetooth keyboard
    
    * Logitech M557 Optical Bluetooth mouse
</span>
-->

<!-- lang: FR -->
<span lang="french">
J'utilise les élements suivants :

- 1 Smartphone Google Nexus 4 16Go  

- 1 Adaptateur Slimport to HDMI, avec Micro-USB pour alimenter simultanément le smartphone  
 
- 1 Clavier Bluetooth Logitech K380  
 
- 1 Souris Bluetooth Optique Logitech M557  
</span>

<!-- lang: EN
<spanspan lang="english">
    The most important convergence bits landed with image r273 of the `ubuntu-touch/rc-proposed/ubuntu` channel. At the time of writing my phone is running image r276 of the same channel.
</span>
-->

<!-- lang FR -->
<span lang="french">
    Les bits les plus important concernant la convergence sont arrivés avec l'image r273 du canal `ubuntu-touch/rc-proposed/ubuntu`. Au moment où j'écris ces lignes, mon téléphone tourne avec l'image r276 du même canal.
</span>


<!-- lang: EN
<span lang="english">
    **NOTE**: I haven't had much luck with anything else than SlimPort to HDMI, especially not when trying to convert the HDMI signal to something else using a second adapter (e.g. Slimport to HDMI and then HDMI to DVI). If you're going to demo Convergence somewhere, make sure the display/projector has HDMI and works with your phone.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    **NOTE :** Je n'ai pas eu beaucoup de chance en essayant autre chose que la connexion du SlimPort vers l'HDMI, et surtout pas en essayant de convertir le signal HDMI vers autre chose en utilisant un deuxième adaptateur (ex: du SlimPort vers l'HDMI, puis de l'HDMI vers le DVI). Si vous souhaitez faire une démo de la convergence quelque part, assurez vous que l'écran/projecteur à l'HDMI et qu'il fonctionne avec votre appareil.
</span>

<!-- lang: EN
## <span lang="english">Setting it up</span>
-->

<!-- lang: FR -->
## <span lang="french">Paramétrage</span>

<!-- lang: EN 
<span lang="english">
    The first step is to test if the SlimPort-to-HDMI adapter works. Hotplugging the external display is quite unreliable and will very often result in the external display only showing half of the picture, as can be seen in the following image:
</span>
-->

<!-- lang: FR -->
<span lang="french">
    La première étape consiste à vérifier si l'adaptateur SlimPort vers HDMI fonctionne. Le branchement à chaud est assez peu fiable et conduira très souvent l'écran externe à ne montrer que la moitié de l'écran comme vous pouvez le voir sur la photo suivante :
</span>

<!-- lang: EN
<span lang="english">
![Hotplug problems][2]
</span>
-->

<!-- lang: FR -->
<span lang="french">
![Problèmes de connexion à chaud][2]
</span>

<!-- lang: EN
<span lang="english">
    So turn off your phone, connect the adapter to the external display and boot the phone:
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Donc éteignez votre téléphone, branchez l'adaptateur à l'écran externe et redemarrez le téléphone :
</span>

<!-- lang: EN
<span lang="english">
![External display has been detected and is being used][3]

![The lockscreen is still the one from the phone UI][4]
</span>
-->

<!-- lang: FR -->
<span lang="french">

![L'écran externe est détecté et utilisé][3]

![L'écran de vérrouillage est encore celui de l'interface utilisateur du téléphone][4]

</span>

<!-- lang: EN
<span lang="english">
    Now we know everything works fine and the phone drives the external display correctly. The phone will currently switch to desktop mode as soon as a mouse is connected, but your USB port is already occupied by the SlimPort adapter and the port cannot do SlimPort and USB data at the same time. So you really need a Bluetooth mouse and keyboard.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Maintenant nous savons que tout fonctionne bien et le téléphone gère correctement l'écran externe. Le téléphone va dès à présent basculer sur le mode bureautique dès qu'une souris sera connectée, mais, votre port USB étant déjà occupé par l'adaptateur SlimPort et le port ne peut pas faire simultanément du SlimPort et du port de données USB en meme temps. Vous allez donc avoir vraiment besoin d'une souris et d'un clavier Bluetooth.
</span>

<!-- lang: EN
## <span lang="english">Set up the Bluetooth devices</span>
-->

<!-- lang: FR -->
## <span lang="french">Paramétrage des dispositifs Bluetooth</span>

<!-- lang: EN
<span lang="english">
    Because the phone touchscreen can no longer be used when an external display is connected, you have to disconnect the phone again, pair the Bluetooth devices and then connect the external display again. This process is straightforward:
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Parce que l'écran tactile du téléphone ne peut plus etre utilisé quand un écran externe est branché, vous devez déconnecter à nouveau le téléphone, appareiller les dispositifs Bluetooth et rebrancher l'écran externe. Cette procédure est simple :
</span>

<!-- lang: EN
<span lang="english">
![Connecting Bluetooth devices][5]

![Bluetooth device details][6]
</span>
-->

<!-- lang: FR -->
<span lang="french">

![Connexion des dispositifs Bluetooth][5]

![Détails des dispositifs Bluetooth][6]

</span>

<!-- lang: EN
## <span lang="english">Finally: Desktop Mode</span>
-->

<!-- lang: FR -->
## <span lang="french">Et pour finir: Le mode bureautique</span>

<!-- lang: EN
<span lang="english">
    You will have noticed that the phone immediately switched its internal display to desktop mode when the Bluetooth mouse was successfully paired:
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Vous avez peut-etre remarqué que votre téléphone bascule son écran interne en mode bureautique lorsque la souris bluetooth est appareillé avec succès:
</span>

<!-- lang: EN
<span lang="english">
![Desktop mode on the internal display][7]
</span>
-->

<!-- lang: FR -->
<span lang="french">
![Mode bureautique sur l'écran interne][7]
</span>

<!-- lang: EN
<span lang="english">
    This is not really useful, so connect the external display again to enjoy full desktop mode :
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Ce n'est pas vraiment utile, donc connectez de nouveau l'écran externe pour profiter pleinement du mode bureautique :
</span>

<!-- lang: EN
<span lang="english">
![Desktop mode on the external display][8]
</span>
-->

<!-- lang: FR -->
<span lang="french">
![Mode bureautique sur l'écran externe][8]
</span>

<!-- lang: EN
<span lang="english">
    This, ladies and gentleman, is Convergence. Still lots of things missing, but we will take care about that in the next part of this series.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Ça, Mesdames et Messsieurs, c'est la Convergence. Il y a encore beaucoup de choses manquantes, mais nous nous en occuperons dans une prochaine partie de cette série.
</span>

**source :** [_Ubuntu Convergence, part 1: Setting it up_][9] sur le [**Blog de Sturm Flut**][10]

[1]: https://sturmflut.github.io//images/ubuntu-convergence-part-1/desk.jpg
[2]: https://sturmflut.github.io//images/ubuntu-convergence-part-1/hotplug.jpg
[3]: https://sturmflut.github.io//images/ubuntu-convergence-part-1/external-connected.jpg
[4]: https://sturmflut.github.io//images/ubuntu-convergence-part-1/external-phone-lockscreen.jpg
[5]: https://sturmflut.github.io//images/ubuntu-convergence-part-1/bluetooth1.jpg
[6]: https://sturmflut.github.io//images/ubuntu-convergence-part-1/bluetooth2.jpg
[7]: https://sturmflut.github.io//images/ubuntu-convergence-part-1/desktop-mode-internal.jpg
[8]: https://sturmflut.github.io//images/ubuntu-convergence-part-1/desktop-mode-external.jpg
[9]: http://sturmflut.github.io/ubuntu/convergence/2015/11/01/ubuntu-convergence-part-1/
[10]: http://sturmflut.github.io/