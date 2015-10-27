---
file: x-marks-the-spot.md
title: "X marque le lieu"
description: 'Mark Suttleworth - Blog post about X name'
author: Mark Shuttleworth
translation: Winael
date: 2015-10-26
category: Ubuntu
tags: Ubuntu,Ubuntu operating system,tablet,smartphone,phone,convergence,lxc,lxd,Snappy,MaaS,Juju,Xenial Xerus,16.04 LTS
viewport: 'width=device-width, initial-scale=1'
---

<meta http-equiv='Content-Type' content='text/html; charset=utf-8' />

<!-- lang: EN
What a great Wily it’s been, and for those of you who live on the latest release and haven’t already updated, the bits are baked and looking great. You can jump the queue if you know where to look while we spin up the extra servers needed for IMG and ISO downloads :)
-->

Comme Wily a été merveilleux, et pour ceux qui seraient encore sur la dernière version et qui ne l'ont pas mis à jour, les bits sont cuits et semblent bons. Vous pouvez sauter la file d'attente si vous savez où chercher pendant que nous faisons tourner les serveurs supplémentaires nécessaires au téléchargement des IMG et des ISO :)

<!-- lang: EN
Utopic, Vivid and Wily have been three intense releases, packed with innovation, and now we intend to bring all of those threads together for our Long Term Support release due out in April 2016.
-->

Utopic, Vivid et Wily ont été trois versions intenses, emballées avec de l'innovation, et maintenant nous avons l'attention de mettre tous ces sujets ensemble pour notre version Support à Long Terme prévue pour Avril 2016.

<div id="LXD-is-the-pure-container-hypervisor" style="float: right;">
  <!--lang: EN
  <img src="http://assets.ubuntu.com/sites/ubuntu/1533/u/img/homepage/lxd_takeover.png" alt="LXD is the lightervisor, a pure-container virtualisation system, the world's fastest hypervisor." style="max-width:100%;display: block;" />
  LXD is the pure container hypervisor
  -->
  <img src="http://assets.ubuntu.com/sites/ubuntu/1533/u/img/homepage/lxd_takeover.png" alt="LXD est le lightervisor, un système de pur conteneur de virtualisation, l'hyperviseur le plus rapide du monde." style="max-width:100%;display: block;" />
  LXD est l'hyperviseur de conteneurs pur
</div>

<!-- lang: EN
**LXD is the world’s fastest hypervisor, led by Canonical, a pure-container way to run Linux guests on Linux hosts.** If you haven’t yet played with LXD (a.k.a LXC 2.0-b1) it will blow you away.  It will certainly transform your expectations of virtualisation, from slow-and-hard to amazingly light and fast. Imagine getting a full machine running any Linux you like, as a container on your laptop, in less than a second. For me, personally, it has become a fun way to clean up my build processes, spinning up a container on demand to make sure I always build in a fresh filesystem.
-->

**LXD est l'hyperviseur le plus rapide du monde, mené par Canonical, une manière en pur conteneur d'exécuter des invités Linux sur des hôtes Linux.** Si vous n'avez pas encore joué avec LXD (aka LXC 2.0 b1) il vous soufflera. Il va certainement transformer vos attentes sur la virtualisation, de lente-et-difficile à étonnamment légère et rapide. Imaginez-vous une machine complète faisant tourner n'importe quel Linux vous aimez, comme un conteneur sur votre ordinateur portable, en moins d'une seconde. Pour moi, personnellement, c'est devenu une façon amusante de nettoyer mes processus de construction, en faisant tourner conteneur à la demande pour m'assurer que je construis toujours dans un nouveau système de fichiers.

<div id="snappy-packaging-system" style="float: left;">
<!-- lang: EN
  <img src="https://assets.ubuntu.com/sites/ubuntu/1253/u/img/cloud/tools/snappy/snappy.png" alt"Snappy packages have transactional updates with rollback." style="max-width:100%;display: block;" />
Snappy Packaging System
-->
  <img src="https://assets.ubuntu.com/sites/ubuntu/1253/u/img/cloud/tools/snappy/snappy.png" alt"Les paquets Snappy ont des mise à jour transactionelles avec retour/arrière." style="max-width:100%;display: block;" />
Système de paquets Snappy
</div>

<!-- lang: EN
**Snappy is the world’s most secure packaging system**, delivering crisp and transaction updates with rollback for both applications and the system, from phone to appliance. We’re using snappy on high-end switches and flying wonder-machines, on raspberry pi’s and massive clouds. Ubuntu Core is the all-snappy minimal server, and Ubuntu Personal will be the all-snappy phone / tablet / pc. With a snap you get to publish exactly the software you want to your device, and update it instantly over the air, just like we do the Ubuntu Phone. Snappy packages are automatically confined to ensure that a bug in one app doesn’t put your data elsewhere at risk. Amazing work, amazing team, amazing community!
-->

**Snappy est le système de paquetse le plus sécurisé du monde**, fournissant des mises à jour nettes et transactionnelles avec retour/arrière pour les applications et le système, du téléphone aux appareils. Nous utilisons Snappy sur les commutateurs haut de gamme et merveilleuses-machines volantes, sur les nuages de Raspberry Pi de nuages ou massifs. Ubuntu Core est le serveur minimal entièrement sous Snappy, et Ubuntu personnel sera le téléphone/tablette/pc entièrement sous Snapppy. En un clin d'oeil vous pouvez publier exactement le logiciel que vous souhaitez sur votre dispositif, et le mettre à jour instantanément par les airs, comme nous le faisons sur le téléphone Ubuntu. Les paquets Snappy sont automatiquement confinés pour veiller à ce que qu'aucun bug dans une application ne prenne le risque de mettre vos données ailleurs. Un travail extraordinaire, une équipe formidable, une incroyable communauté !

<div id="metal-as-a-service" style="float: right;">
<!-- lang: EN
  <img src="http://maas.ubuntu.com/wp-content/uploads/2013/01/maas-logo.png" alt="MAAS is your physical cloud
Metal as a Service." style="max-width:100%;display: block;" />
Metal as a Service
-->
  <img src="http://maas.ubuntu.com/wp-content/uploads/2013/01/maas-logo.png" alt="MAAS est votre nuage physique de Métal en tant que Service." style="max-width:100%;display: block;" />
Métal en tant que Service
</div>

<!-- lang: EN
**MAAS is your physical cloud**, with bare-metal machines on demand, supporting Ubuntu, CentOS and Windows. Drive your data centre from a single dashboard, bond network interfaces, raid your disks and rock the cloud generation. Led by Canonical, loved by the world leaders of big, and really big, deployments. MAAS gives you high availability DNS, DHCP, PXE and other critical infrastructure, for huge and dynamic data centres. Also pretty fun to run at home.
-->

**MAAS est votre nuage physique**, avec des serveurs physiques à la demande, supportant Ubuntu, CentOS et Windows. Gérer votre centre de données à partir d'un seul tableau de bord, les interfaces réseau obligataire, le RAID de vos disques et secouez la génération de nuage. Mené par Canonical, aimé par les leaders mondiaux de grands et très grands déploiements. MAAS vous donne une haute disponibilité DNS, DHCP, PXE et autres infrastructures essentielles, pour des centres de données énormes et dynamiques. C'est également assez amusant d'en faire tourner à la maison.

<!-- lang: EN
**Juju is… model-driven application orchestration**, that lets communities define how big topological apps like Hadoop and OpenStack map onto the cloud of your choice. The fastest way to find the fastest way to spin those applications into the cloud you prefer. With traditional configuration managers like Puppet now also saying that model-driven approaches are the way to the future, I’m very excited to see the kinds of problems that huge enterprises are starting to solve with Juju, and equally excited to see start-ups using Juju to speed their path to adoption. Here’s the Hadoop, Spark, IPython Notebook coolness I deployed live on stage at Apache Hadoopcon this month:
-->

**Juju est... notre application d'orchestration gérée par modèle**, qui laisse aux communautés le choix de définir comment les grande applications topologiques comme Hadoop et OpenStack s'intègrent sur le nuage de votre choix. Le moyen le plus rapide de trouver le moyen de faire tourner ces applications le plus rapidement possible dans le nuage que vous préférez. Avec les gestionnaires de configuration traditionnels comme Puppet qui disent également maintenant que les approches gérées par modèles sont la voie de l'avenir, je suis très heureux de voir le genre de problèmes que d'énormes entreprises commencent à résoudre avec Juju, et tout aussi heureux de voir des start-ups utilisant Juju pour accélérer leur chemin vers l'adoption. Voici Hadoop, Spark, IPython Notebook que j'ai fraîchement déployé sur scène pendant l'Apache Hadoopcon ce mois-ci :

<div id="apache-hadoop-spark-ipython-modelled-with-juju">
<!-- lang: EN
  <img src="https://www.markshuttleworth.com/wp-content/uploads/2015/10/ff6a/apache-hadoop-spark.png" alt="Juju model of Apache Hadoop with Spark and IPython Notebook" style="max-width:100%;display: block;" />
Apache Hadoop, Spark, IPython modelled with Juju
-->
  <img src="https://www.markshuttleworth.com/wp-content/uploads/2015/10/ff6a/apache-hadoop-spark.png" alt="Modèle Juju d'Apache Hadoop avec Spark et IPython Notebook" style="max-width:100%;display: block;" />
Apache Hadoop, Spark, IPython modelé avec Juju
</div>

<!-- lang: EN
All of these are coming together beautifully, making Ubuntu the fastest path to magic of all sorts. And that magic will go by the codename… **xenial xerus**!
-->

Tout ça se rassemble magnifiquement, faisant d'Ubuntu le chemin le plus rapide vers toute sorte de magie. Et cette magie va avoir comme nom de code ... **xenial xerus** !

<!-- lang: EN
What fortunate timing that our next LTS should be X, because “xenial” means “friendly relations between hosts and guests”, and given all the amazing work going into LXD and KVM for Ubuntu OpenStack, and beyond that the interoperability of Ubuntu OpenStack with hypervisors of all sorts, it seems like a perfect fit.
-->

Quelle calendrier chanceux que notre prochaine LTS devait être X, parce que « xenial » signifie « des relations amicales entre les hôtes et les invités », et compte tenu de tout le travail incroyable pour l'intégration de LXD et KVM dans Ubuntu OpenStack, et au-delà pour l'interopérabilité d'Ubuntu OpenStack avec des hyperviseurs de toutes sortes, cela ressemble à un ajustement parfait.

<!-- lang: EN
And Xerus, the African ground squirrels, are among the most social animals in my home country. They thrive in the desert, they live in small, agile, social groups that get along unusually well with their neighbours (for most mammals, neighbours are a source of bloody competition, for Xerus, hey, collaboration is cool). They are fast, feisty, friendly and known for their enormous… courage. That sounds just about right. With great… courage… comes great opportunity!
-->

Et Xerus, les [écureuils de terre][2] africains, sont parmi les animaux les plus sociales dans mon pays d'origine. Ils prospèrent dans le désert, ils vivent en petits groupes sociaux, agile, qui s'accomodent exceptionnellement bien avec leurs voisins (pour la plupart des mammifères, les voisins sont une source de sanglante concurrence, pour Xerus, hey, la collaboration est un truc de cool). Ils sont rapides, fougueux, amicaux et connu pour leur énorme... courage. Cela semble à peu près normal. Avec beaucoup... de courage... viennent de grandes opportunités !

**source :** [*X marks the spot*][3] sur le [blog de Mark Shuttleworth][4]
 
[1]: http://assets.ubuntu.com/sites/ubuntu/1533/u/img/homepage/lxd_takeover.png
[2]: https://fr.wikipedia.org/wiki/Xerus_inauris
[3]: http://www.markshuttleworth.com/archives/1479
[4]: http://www.markshuttleworth.com
