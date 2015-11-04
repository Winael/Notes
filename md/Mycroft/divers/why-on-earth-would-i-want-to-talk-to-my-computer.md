---
file: why-on-earth-would-i-want-to-talk-to-my-computer.md
title: "Pourquoi sur Terre voudrais-je parler à mon ordinateur ?"
author: Joshua Montgomery
translation: Winael
date: 2015-11-02
category: Mycroft
tags: Mycroft, GUI, interface utilisateur
status: review_in_progress
viewport: 'width=device-width, initial-scale=1'
---

<meta http-equiv='Content-Type' content='text/html; charset=utf-8' />

<!-- Chapeau -->

**Joshua Montgomery est le CEO et fondateur de Mycroft AI, une startup texane qui cherche à lancer un module opensource d'Intelligence Artificielle domestique. Il nous livre ici sa vision de l'avenir de l'interface utilisateur utilisant le langage naturel. Bonne lecture !**

<!-- lang: EN
# <span lang="english">Why On Earth Would I Want To Talk To My Computer?</span>
-->

<!-- lang: FR -->
# <span lang="french">Pourquoi sur Terre voudrais-je parler à mon ordinateur ?</span>

![][1]

<!-- lang: EN
<span lang="english">
When I started my first computer job in 2000 I was fortunate enough to work with a PhD named Dan Vasacheck who took the time to show me how to use the company’s Unix mainframe. Though I learned a lot from Dan, the best gem of wisdom I took away was this – “A graphic user interface (GUI) is the equivalent of pointing and grunting, the command line interface (CLI) allows you to have a conversation with your computer.”
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Quand je commencé mon premier emploi en informatique en 2000, j'ai eu la chance de travailler je fus assez heureux de travailler avec un titulaire de doctorat nommé Dan Vasacheck qui a pris le temps de me montrer comment utiliser l'ordinateur central Unix de l'entreprise. Bien que j'ai beaucoup appris de Dan, voici la meilleure perle de de sagesse que j'ai gardé - _« Une interface utilisateur graphique (GUI) est l'équivalent de poiter et grogner, l'interface en ligne de commande (CLI) vous permet d'avoir une conversation avec votre l'ordinateur. »_
</span>

<!-- lang: EN
<span lang="english">
You see, to use a windows interface, all you really need to do is move the mouse cursor to a specific part of the screen (point) and click (grunt). In fact, when multi-touch technology became available in 2005 it was hailed as a huge advancement in human-machine interaction. You can now zoom-in and out too. Wow! It is like we are developing stone age tools all over again.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Vous voyez, pour utiliser une interface de fenêtres, tout ce que vous avez vraiment besoin de faire est de déplacer le curseur de la souris sur une partie spécifique de l'écran (point) et cliquez (grogner). En fait, quand la technologie multi-touch est devenu disponible en 2005, elle a été saluée comme un progrès énorme dans l'interaction homme-machine. Vous pouvez maintenant zommer et dézoomet. Hou la la ! C'est comme si nous développions des outils de l'âge de pierre encore une fois.
</span>

<!-- lang: EN
<span lang="english">
The CLI, on the other hand, allows you to have a conversation with the computer, all be it in the computers stilted language. Programmers developed a series of programs and utilities layered on a command shell. Since programmers are lazy by nature they abbreviated the program names (“list” became “ls” for example) and gradually added a series of settings or options in the form of command line flags. To use the CLI you need to know which commands to run, which flags are applicable and how to string commands together. If you know the secrets of this language you can converse with your computer in ways that seem like magic to GUI users. As an example, to scan a remote network and get the ip addresses of computers that are responding to ICMP you would type:
</span>
-->

<!-- lang: FR -->
<span lang="french">
    La CLI, d'un autre coté, vous permet d'avoir une conversation avec l'ordinateur, le tout dans la langue de bois des ordinateurs. Les programmeurs ont développé une série de programmes et de services en couches dans un interpréteur de commande. Puisques les programmeurs sont paresseux par nature, ils ont abrégé les noms de programmes (_« liste »_ est devenu "`ls`" par exemple) et ajoutés progressivement une série de paramètres ou des options sous la forme d'indicateurs de ligne de commande. Pour utiliser la CLI vous avez besoin de savoir quelle commande utiliser, qui indicateurs sont applicables et comment enchaîner les commandes ensemble. Si vous connaissez les secrets de cette langue, vous pouvez converser avec votre ordinateur d'une manière qui semblent magique pour les utilisateurs de l'interface graphique. A titre d'exemple, pour analyser un réseau distant et obtenir les adresses IP des ordinateurs qui répondent à ICMP vous devez taper :
</span>

```sh
nmap -sP -n -v 10.0.0.0/24 2> /dev/null | grep -i ‘to be up’ | cut -d ” ” -f 2
```

<!-- lang: EN
<span lang="english">
However, structuring this command takes time and expertise. It is often done by trial and error and even accomplished users of the command line need to constantly refer to the user manual. Why? Because the syntax is archaic, there are no real standards between commands (does “-n” mean new or null?) and even slightly different versions of the same shell have different syntax.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Cependant, la structuration de cette commande prend du temps et de l'expertise. Elle est souvent faite par essais et erreurs et même les utilisateurs chevronnés de la ligne de commande doivent constamment se référer au manuel d'utilisation. Pourquoi ? Parce que la syntaxe est archaïque, il n'y a pas de véritables normes entre les commandes (est-ce que "`-n`" signifie _« nouveau »_ ou _« nul »_) Et même des versions légèrement différentes du même interpréteur de commandes ont une syntaxe différente.
</span>

<!-- lang: EN
<span lang="english">
To put it in layman’s terms the CLI is the equivalent of a formal letter. It can be used to communicate just about anything, but it is far too clunky for our daily needs. You don’t send the grocer a formal letter asking where they keep the pumpkin pie filling, you simply walk up to him and ask.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Pour le dire en termes simples la CLI est l'équivalent d'une lettre officielle. Elle peut être utilisé pour communiquer sur à peu près tout, mais elle est bien trop mal foutue pour nos besoins quotidiens. Vous n'envoyez pas une lettre officielle à l'épicier une lettre officielle demandant où est conservé la garniture de tarte à la citrouille, vous marchez simplement vers lui et vous lui demandez.
</span>

<!-- lang: EN
<span lang="english">
There’s a better way. Natural language recognition – the type of communication we every day to communicate with other people. Until recently this type of computer interface was beyond the reach of computer science, but it is now becoming widely available as companies like Facebook, Google, Apple, Microsoft and Amazon have invested in M, Now, Siri, Cortana and Echo respectively.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Il ya une meilleure façon. La reconnaissance du langage naturel - le type de communication que nous utilisons tous les jours pour communiquer avec d'autres personnes. Jusqu'à récemment, ce type d'interface d'ordinateur était au-delà de la portée de la science informatique, mais elle est maintenant de plus en plus largement disponibles au alors que des entreprises comme Facebook, Google, Apple, Microsoft et Amazon ont investi respectivement dans M, Google Now, Siri, Cortana et Echo.
</span>

<!-- lang: EN
<span lang="english">
So why are these companies making billion dollar investments in natural language interfaces? Because it’s the future of the human computer interface. We’ve spent the last 50 years teaching people to speak the language of the machines. It is difficult, awkward and takes years of experience. We are now at a place where we can teach machines to speak the language of humans – intuitive, easy to use and natural. With natural language processing, I can have my computer scan a remote network by simply saying:
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Alors pourquoi ces entreprises font des milliards de dollars d'investissements dans les interfaces en langage naturel ? Parce c'est l'avenir de l'interface homme-machine. Nous avons passé les 50 dernières années à apprendre aux gens à parler la langue des machines. C'est difficile, maladroit et ça prend des années d'expérience. Nous sommes maintenant à un moment où nous pouvons enseigner aux machines à parler la langue des humains - intuitive, facile à utiliser et naturelle. Avec le traitement du langage naturel, je peux avoir mon ordinateur qui numérise un réseau distant en disant simplement :
</span>

<!-- lang: EN
<span lang="english">
>_"Hey, Mycroft. Run a ping sweep of 10.1.1.0/24 and list the IPs in use."_
</span>
-->

<!-- lang: FR -->
> <span lang="french">_« Hey, Mycroft. Exécute un balayage de ping sur le sous-réseau 10.1.1.0/24 et liste-moi les adresses IP en cours d'utilisation. »_
</span>

<!-- lang: EN
<span lang="english">
-or-
</span>
-->

<!-- lang: FR -->
<span lang="french">
    -ou-
</span>

<!-- lang: EN
<span lang="english">
> _"Hey, Mycroft. Which IPs on 10.1.1.0/24 are returning ICMP?"_
</span>
-->

<!-- lang: FR -->
> <span lang="french">_« Hey, Mycroft. Quelles adresses IPs retournent ICMP sur le sous-réseau 10.1.1.0/24 ? »_</span>

<!-- lang: EN
<span lang="english">
The natural language processing in the system translates my speech into a series of commands, executes them, and then provides a listing of the results. There is no standard syntax, I give the command naturally and the computer interprets the results. No need to memorize flags, pipe output from one command to another, or worry about throwing the wrong flag. The underlying skill ( which in this case was developed by someone who IS an expert in the CLI and in nmap ) handles the arcane language and provides a neatly formatted list of IP addresses.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Le traitement du langage naturel dans le système traduit mon discours en une série de commandes, les exécute, puis fournit une liste des résultats. Il n'y a aucune syntaxe standard, je donne la commande naturellement et l'ordinateur interprète les résultats. Pas besoin de mémoriser des indicateurs, les sortie de tuyaux d'une commande à l'autre, ou de se soucier de d'utiliser le mauvais indicateur. La compétence sous-jacente (qui dans ce cas présent a été développé par quelqu'un qui est un expert en CLI et en `nmap`) gère le langage des arcanes et fournit une liste proprement formatée d'adresses IP.
</span>

<!-- lang: EN
<span lang="english">
Skeptical? I understand. Users have a right to be skeptical, especially power users who use the CLI all day. Vendors have been selling broken and essentially useless voice command software for more than 15 years now. Even today my Chevy Volt is a prime example – it has a terrible voice interface that is effectively useless. Worse, it is closed source and proprietary so I can’t simply replace it with Mycroft or hack it to suite my needs, but that is changing.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Sceptique? Je comprends. Les utilisateurs ont le droit d'être sceptiques, en particulier les utilisateurs qui utilisent la ligne de commande toute la journée. Les vendeurs ont vendu des logiciels de commande vocales cassés et essentiellement inutiles pendant plus de 15 ans maintenant. Même aujourd'hui, mon Chevy Volt est un excellent exemple - il a une interface vocale terrible qui est effectivement inutile. Pire, il est ses sources sont fermées et propriétaires, donc je ne peux pas tout simplement le remplacer par Mycroft ou le bidouiller pour qu'il convienne à mes besoins, mais c'est en train de changer.
</span>

<!-- lang: EN
<span lang="english">
Here at Mycroft we are developing an open source AI that will allow anyone with an idea to develop a skill and deploy it globally. Want to make it easy for end users to get the score of the latest FIFA football game? Use our standard template to develop the skill, upload it to our repository and soon every Mycroft user on earth will be able to follow the latest from any FIFA game.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Ici, à Mycroft nous développons une Intelligence Opensource qui permettra à quiconque ayant une idée de développer une compétence et de la déployer globalement. Vous voulez rendre facile pour les utilisateurs finaux d'obtenir le score du dernière match de football de la FIFA ? Utilisez notre modèle standard pour développer la compétence, charger la sur notre dépôt et rapidement chaque utilisateur Mycroft sur la terre sera en mesure de suivre la derniers scores de tout jeu de la FIFA.
</span>

<!-- lang: EN
<span lang="english">
The technology to make a natural language interface is here today. We can build an interface that is intuitive, easy to use, flexible and friendly. Billions of people are using early versions on their Apple, Android and Windows devices. In the future these interfaces will be an important part of any modern consumer operating system in much the same way that the GUI became a key component in the 1980’s.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    La technologie pour faire une interface en langage naturel est là aujourd'hui. Nous pouvons construire une interface qui est intuitive, facile à utiliser, flexible et conviviale. Des milliards de personnes utilisent les premières versions sur leurs appareils Apple, Android et Windows. Dans l'avenir, ces interfaces seront un élément important de tout système d'exploitation de consommation moderne de la même manière que l'interface graphique est devenu un élément clé dans les années 1980.
</span>

<!-- lang: EN
<span lang="english">
You will eventually spend your day talking with your computer, and it’s going to be great.
</span>
-->

<!-- lang: FR -->
<span lang="french">
    Vous allez finir par passer votre journée à parler avec votre ordinateur, et ça va être génial.
</span>

**source :** [_Why on Earth would I talk to my computer?_][2] sur le blog de [Mycroft AI][3]

[1]: /home/winael/Documents/Notes/fig/Mycroft/divers/Voice.png
[2]: https://mycroft.ai/why-on-earth-would-i-want-to-talk-to-my-computer/
[3]: https://mycroft.ai