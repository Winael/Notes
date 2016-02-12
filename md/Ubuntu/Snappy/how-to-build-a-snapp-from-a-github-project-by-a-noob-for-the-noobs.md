---
file: how-to-build-a-snapp-from-a-github-project-by-a-noob-for-the-noobs.md
title: "How to build a snapp from a Github project, by a noob for the noobs"
author: Winael
date: 2016-02-10
category: How-to
tags: Snappy,Ubuntu,Snapp,Etherpad-lite
---

<meta http-equiv='Content-Type' content='text/html; charset=utf-8' />

<!-- Chapeau -->

**For those who don't know me yet, let me introduce myself. Even I'm an Official Ubuntu Member, I'm not a techie one. I'm more known for my work as Evangelist. I like popularize techies knowledge to make them more understandable for the mass.**

**I'm a big fan of etherpad-lite. I use this service a lot from FramaCloud, a project host by Framasoft, a french non-profit organisation of Free software advocates. But I think that could be for the best if I could host my own etherpad-lite on my Rasperry Pi 2 running Ubuntu Snappy, with a snapp package. I don't want to wait anymore, so I decided to create my first snapp, the etherpad-lite one. I know, for a noob it's a pretty big thing, it's like climbing the Mont-blanc as a noob.**

**Fortunately, there's some great people on the Community, that could be very good Sherpas. So I'll not be alone in this adventure, and I will try to explain all I understand as a nood and share this experience with you guys... So let's do this***

<!-- Fin Chapeau -->

## Study the traditional procedure

So to begin, we need to read and understand the instruction to install etherpad in a traditional way.

For Ubuntu, all the instructions are [here][1].

> You'll need gzip, git, curl, libssl develop libraries, python and gcc.
> 
> ````sh
> apt-get install gzip git curl python libssl-dev pkg-config build-essential
> ````
> 
> Additionally, you'll need node.js installed, Ideally the latest stable version, we recommend installing/compiling nodejs from source (avoiding apt).
> 
> As any user (we recommend creating a separate user called etherpad):
>   - Move to a folder where you want to install Etherpad. 
>   - Clone the git repository 
> 
> ````sh
> git clone git://github.com/ether/etherpad-lite.git
> ````
>    
>   - Change into the new directory containing the cloned source code 
> 
> ````sh
> cd etherpad-lite
> ````
> 
> Now, run `bin/run.sh` and open http://127.0.0.1:9001 in your browser.
> 
> Update to the latest version with `git pull origin`. The next start with `bin/run.sh` will update the dependencies.

Ok. So we have dependances to install, we have to clone the repository of etherpad-lite, and run a script from this cloned repo that will launch InstallDeps.sh (check the dependances, load your personal setting, and build the node module), and then run the node module.

That seems pretty simple. So now how we could snapp it ?

## How works the app ?

Don't be in a hurry, before to snapp the app, we'll have to know how it works.

So I the procedure said, to launch etherpad-lite, we have to run `bin/run.sh`. But what does this script shell ?



## The `snapcraft.yaml` file

So, first of all, we'll need to create a folder etherpad-lite, where we will build our snapp and move in there.

````sh
mkdir etherpad-lite && cd etherpad-lite
````







[1]: https://github.com/ether/etherpad-lite#gnulinux-and-other-unix-like-systems
