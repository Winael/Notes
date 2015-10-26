---
file: la-maison-ouverte-aux-applications-phase-i-definir-l-interface.md
title: "La maison ouverte aux applications, Phase I : Définir l'Interface"
author: JBerg
translation: Winael
date: 2015-10-09
category: Internet des Objets
tags: firstbuild, General Electrics, Snappy, Canonical, Ubuntu, IoT, Internet des Objets
---

<meta http-equiv='Content-Type' content='text/html; charset=utf-8' />

**Afin de développer l'Internet des Objets (IoT ou IdO) domestique, FirstBuild de General Electrics, en partenariat avec Canonical, la société sponsor du projet Ubuntu, lance un grand concours afin de définir une nouvelles norme universelle opensource, basée sur Ubuntu Snappy Core.**

**La première phase de consultation se terminera le 12 octobre 2015.**

----------

<!-- Lang: EN
# Challenge brief
-->

# Résumé du défi

<!-- Lang: EN
## Crowdsourcing the App-Enabled Home
-->

## Production participative de la Maison ouverte aux Applications 

<!-- Lang: EN
Connected and smart devices making up the internet of things (referred to as IoT) have the potential to revolutionize the way we interact with our home and more importantly, how our home interacts with us. Imagine a home that is supported by apps and app stores on any type of home appliance. Earlier this year, GE’s FirstBuild brought to market [the first open, app-enabled fridge][1]. This brings the vision of IoT one step closer but it is not yet a mass market solution. There are too many competing standards, both open and proprietary. In order for IoT to be truly be ubiquitous, several friction points need to be resolved.
-->

Les dispositifs connectés et intelligents qui composent l'internet des objets (dénommé IdO) ont le potentiel de révolutionner la façon dont nous interagissons avec notre maison et, plus important encore, comment notre maison interagit avec nous. Imaginez une maison qui est pris en charge par des applications et des magasins d'applications sur tout type d'appareil à domicile. Plus tôt cette année, FirstBuild de GE a mis sur le marché [le premier réfrigérateur ouvert aux applications][1]. Cela porte à un pas de plus la vision de l'IdO, mais ce n'est pas encore une solution de marché de masse. Il y a trop de normes concurrentes, à la fois ouvertes et propriétaires. Pour que l'IdO puisse être vraiment omniprésent, plusieurs points de friction doivent être résolus.

<!-- Lang: EN
- How can developers create apps for different appliances and competing brands?
- What hardware and software can enable these apps?
- Can the hardware be designed to interface with multiple appliances, and appliance manufacturers?
- Can this hardware interface be constructed in a way to make the control upgradeable, so the consumer can easily refresh the appliance features d without having to buy another fridge or dishwasher?
- How can an appliances be manufactured “IoT-ready” without adding extra costs for consumers that don’t want IoT just yet?
-->

- Comment les développeurs peuvent créer des applications pour différents appareils et marques concurrentes ?
- Quels matériels et logiciels peuvent permettre ces applications ?
- Le matériel peut-il être conçu pour s'interfacer avec plusieurs appareils, et fabricants d'appareils ?
- Cette interface matérielle peut-elle être construite de manière à rendre le contrôle évolutif, afin que le consommateur puisse facilement rafraîchir l'appareil dont il dispose sans avoir à acheter un autre réfrigérateur ou lave-vaisselle ?
- Comment un appareils peut-il être fabriqués "IdO-ready" sans ajouter de coûts supplémentaires pour les consommateurs qui ne veulent pas encore IdO ?

<!-- Lang: EN
## Pluggable hardware for home appliances
-->

## Matériel enfichable pour les appareils ménagers

<!-- Lang: EN
Long-lived app-enabled home appliances will need a simple way to plugin a micro-server, power this micro-server and connect the micro-server to the appliance’s microcontroller. This contest is about defining an open standard for any chip or controller to be easily plugged into any smart home appliance.
-->

À long terme les appareils ménagers ouverts aux applications auront besoin d'un moyen simple de pouvoir brancher un micro-serveur, d'alimenter ce micro-serveur et de connecter le micro-serveur au microcontrôleur de l'appareil. Ce concours consiste à définir un standard ouvert pour toute puce ou un contrôleur pouvant être facilement branché sur un appareil de la maison intelligente.

<!-- Lang: EN
## Why not a regular standardization organization?
-->

## Pourquoi pas une organisation ordinaire de normalisation ?

<!-- Lang: EN
Making a standard through the traditional approach of standardization bodies is slow and painful. GE’s FirstBuild is already selling app-enabled appliances and needs a standard now. Most IT standards today are standards through adoption and not through committee. Crowdsourcing and contests are already heavily used by GE’s FirstBuild for which using the same formula to define a standard is an obvious next step. The outcome will be published on github and open sourced, hence anybody will be able to build a board that is compliant. The objective is to make this standard applicable to any type of home appliance from any vendor and even be applicable outside of the home. The idea, however, is not to reinvent something new if a combination of existing standards solves the problem. Ideally, existing standards from other industries can be reapplied in a new way to fix the above problems.
-->

Faire une norme par l'approche traditionnelle des organismes de normalisation est lente et douloureuse. FirstBuild de GE vend déjà des appareils ouverts aux applications et a besoin d'une norme maintenant. La plupart des normes informatiques d'aujourd'hui sont des normes grâce à l'adoption et non pas par le biais de comité. La production participative et les concours sont déjà fortement utilisées par FirstBuild de GE et utiliser la même formule pour définir une norme est une prochaine étape évidente. Le résultat sera publié sur github et en open source, tout le monde sera donc en mesure de construire une carte qui sera conforme. L'objectif est de faire que cette norme soit applicable à tout type d'appareil de la maison pour tout fournisseur et même être applicable à l'extérieur de la maison. L'idée, cependant, est de ne pas réinventer quelque chose de nouveau si une combinaison des normes existantes résout le problème. Idéalement, les normes existantes provenant d'autres industries peuvent être réappliqués de façon nouvelle façon afin résoudre les problèmes ci-dessus.

<!-- lang: EN
## Why is a standard important for developers?
-->

## Pourquoi une norme est-elle si importante pour les développeurs ?

<!-- lang: EN
Developers want easily available, well supported and price effective boards that are used at large scales inside home appliances. This makes writing apps a lot easier. If every type of device and appliance is unique, then any app needs to be cross-compiled, packaged differently, etc. For this reason GE Appliances, FirstBuild and Canonical, the company behind Ubuntu, are working together to make creating apps really easy via the open source [snappy Ubuntu Core][2] IoT operating system.
-->

Les développeurs veulent des cartes facilement accessibles, bien supportées et efficaces sur les prix à grande échelle, à l'intérieur des appareils ménagers. Cela rend beaucoup plus facile l'écriture d'application. Si chaque type d'appareil et chaque appareil est unique, alors toute application doit être compilé de manière croisée, empaquetée différemment, etc. Pour cette raison, GE Appliances, FirstBuild et Canonical, la société derrière Ubuntu, travaillent ensemble pour que créer des applications soit vraiment facile via le système d'exploitation open source [Snappy Ubuntu Core][2] pour l'IdO.

<!-- lang: EN
See this [Press Release][3] for more on the impact of this challenge
-->

Voir ce [Communiqué de presse][3] pour en savoir plus sur l'impact de ce défi

<!-- lang: EN
# Requirements
-->

# Exigences

<!-- lang: EN
- Define the form factor, attachment method, and location of module and connections relative to common appliances
- Microcontrollers to be integrated via connectable interface (USB, ethernet, etc)
- The new standard should be compatible with existing base connecting technologies (adapters possible to USB/ethernet)
- Standard shall be compatible with micro-servers having minimum of 512MB memory (ideally has 1GB+), 4GB of storage, and an ARM v7/8 or x86 based processor
- Identify input power source
-->

- Définir le facteur de forme, la méthode de fixation, et l'emplacement du module et les connexions par rapport à des appareils communs
- Les microcontrôleurs à être intégrés via une interface connectable (USB, Ethernet, etc.)
- La nouvelle norme devrait être compatible avec les technologies de base de connexion existants (adaptateurs possibles USB / Ethernet)
- Le standard doit être compatible avec les micro-serveurs ayant minimum de 512 Mo de mémoire (idéalement plus de 1Go), 4 Go de stockage, et une v7 ARM / 8 ou processeur x86
- Identifier la source de puissance d'entrée

<!-- lang: EN
## Guidelines
-->

## Lignes directrices

<!-- lang: EN
- Your design should anticipate likely operating systems, protocol hosts, and external protocols.  Discussion of these will show the robustness of your entry.
- With millions of appliances produced every year, keeping cost to a minimum is key to avoid driving price increases to products.
- Appliances shall function without micro-server, but have additional features/functionality when a micro-server is present
- Features of the micro-server shall not be defined by the standard
- Interface is ideally applicable for a variety of major home appliances (refrigerator, range, microwave, dishwasher, laundry, water systems, and room comfort)
- For reference, functionality is desired beyond these existing options:
  - [FirstBuild Green Bean][4]
  - [GE Connect+][5]
-->

- Votre conception doit pouvoir anticiper les systèmes d'exploitation, les hôtes de protocole, et les protocoles externes. Une discussion sur ce sujet montrera la solidité de votre entrée.
- Avec des millions d'appareils produits chaque année, garder le cout à un minimum est la clé pour éviter de conduire à des augmentations de prix des produits.

- Les appareils doivent fonctionner sans micro-serveur, mais avoir des options et des fonctionnalités supplémentaires quand un micro-serveur est présent

- Les caractéristiques du micro-serveur ne sont pas définis par la norme

- L'interface est idéalement applicable pour une grande variété des appareils ménagers les plus courant (réfrigérateur, cuisinière, lave-vaisselle, la lessive, les systèmes d'eau, et le confort de la chambre)

- Pour référence, la fonctionnalité est souhaitée au-delà de ces options existantes:
   
    - [FirstBuild Green Bean] [4]
    
    - [GE Connect +] [5]

<!-- lang: EN
## Additional Deliverables
-->

## Livrables supplémentaires

<!-- lang: EN
- Required image views or CAD files
  - Rendering of physical components of module
  - Rendering of controls interface with 2 common appliances
- BUS Structure Definition between microserver and micro-controller

-->

- Obligation de vues d'images ou de fichiers de CAO

    - Rendu des composants physiques de modules
    
    - Rendu de l'interface de contrôle avec 2 appareils communs
    
- Définition de la structure du BUS entre le microserveur et le micro-contrôleur

Bonne chance à tous.

_Source : [App Enabled Home, Phase I: Define the Interface][6]_

[1]: https://firstbuild.com/smart-refrigerator/
[2]: http://ubuntu.com/things
[3]: http://www.businesswire.com/news/home/20150921006424/en/GE%E2%80%99s-FirstBuild-Leads-Industry-Standard-IoT-Appliances
[4]: https://firstbuild.com/greenbean/
[5]: http://www.geappliances.com/ge/connected-appliances/
[6]: https://firstbuild.com/JBerg/app-enabled-home-phase-i-define-the-interface/brief