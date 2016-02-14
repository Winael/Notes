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

**I'm a big fan of etherpad-lite. I use this service a lot from FramaCloud, a project host by Framasoft, a french non-profit organisation of Free software advocates. But I think that could be for the best if I could host my own etherpad-lite on my Rasperry Pi 2 running Ubuntu Snappy, with a snapp package. But it still doesn't exist and I don't want to wait anymore, so I decided to create my first snapp, the etherpad-lite one. I know, for a noob it's a pretty big thing, it's like climbing the Mont-blanc as a noob.**

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

So I the procedure said, to launch etherpad-lite, we have to run `bin/run.sh`. But what does this script shell ? [Let's take a look to the script][2]

We can see that it will launch a shell script `bin/installDeps.sh` to prepare the environment and then launch a javascript, `node_modules/ep_etherpad-lite/node/server.js with nodejs`

Now, [let's take a look to `bin/installDeps.sh`][3], it will check the dependancies, build the node_modules, download and install all the things needed by etherpad-lite.

## Install snapcraft

To build a snapp, the most common way is to use snapcraft, a tool designed by Canonical and Ubuntu's developers to help people to easely create snapp.

First, you need to add the PPA to get the latest version of Snapcraft:

````sh
$ sudo apt-add-repository ppa:snappy-dev/tools
$ sudo apt update
````

Then, install the snappy-tools, that include snapcraft:

````sh
$ sudo apt install snappy-tools
````

<div class=note>
**note:** You can create snapp from Windows or Mac, using Vagrant, and an image of Ubuntu and install snapcraft on it
</div>

## The `snapcraft.yaml` file

Now that Snapcraft is installed on your machine, you'll need to create the `snapcraft.yaml` that needed to snapcraft to buils your snapp.

First of all, we'll need to create a folder we call `etherpad-lite`, where we will build our snapp. When the folder is created, move in there.

````sh
mkdir etherpad-lite && cd etherpad-lite
````

Then we will use ths `snapcraft init` command to generate the `snapcraft.yaml` file:

````sh
$ snapcraft init
Wrote the following as snapcraft.yaml.

name: # the name of the snap
version: # the version of the snap
# The vendor for the snap (replace 'Vendor <email@example.com>')
vendor: Vendor <email@example.com>
summary: # 79 char long summary
description: # A longer description for the snap
icon: # A path to an icon for the package
````

So now edit the `snapcraft.yaml` file with your favorite editor. Personnaly il like nano a lot:

````sh
nano snapcraft.yaml
````

See how my `snapcraft.yaml` file looks like after a first editing:

````yaml 
name: etherpad-lite-unofficial # the name of the snap
version: 0.1 # the version of the snap
# The vendor for the snap (replace 'Vendor <email@example.com>')
vendor: Winael <vinzjobard@ubuntu.com>

summary: Etherpad-lite, eally-real time collaborative editor # 79 char long summary
description: Etherpad is a really-real time collaborative editor maintained by the Etherpad Community # A longer description for the snap
icon: icon.png # A path to an icon for the package
````

I called it `etherpad-lite-unofficial` because I'm not a member of the Etherpad Community, so the Etherpad community will not be responsible of this snapp. If you have any troubles, please contact me. That's why I put my nickname and email as the `vendor`. 

**Warning:** the name values doesn't accept space or specials characters

You could see a summary and description of the snapp, and where to found the icon you'll see in webdm. I create the icon with Gimp, and place at the root of my `etherpad-lite` folder.

### First part: etherpad-lite

Now we will give all the instructions to build the part of our snapp, etherpad-lite, from the source.

so it's a _nodejs_ app, host on github, that need severals dependances (gzip, git, curl, libssl develop libraries, python and gcc)

In the `snapcraft.yaml` file, we'll add this entry:

````yaml
parts:
  etherpad-lite:
    plugin: nodejs
    source: git://github.com/ether/etherpad-lite
    stage-packages: 
      - gzip 
      - git 
      - curl 
      - python 
      - libssl-dev 
      - pkg-config 
      - build-essential
````

So, your `etherpad-lite` have two file, the `snapcraft.yaml` file and the `icon.png` file:

````sh
$ ls
icon.png  snapcraft.yaml
````

Now, I will do a first test, using the `snapcraft stage` command that allow to test or build step by step

````sh
$ snapcraft stage
````

When done, you'll see that Snapcraft created lots of things:

````sh
$ ls
icon.png  snap          stage
parts     snapcraft.yaml
````

- The `snap` folder is where Snapcraft build the snapp.
- The `stage` folder is where Snapcraft build all it need during the different stage. Useful to debug
- The `parts` folder contains all the things the parts need to be build

So, now, we expect that the `bin` folder in the `stage` directory contains our etherpad-lite app... But no. Snapcraft couldn't make it.

````sh
$ ls stage/bin
node  npm
````

If we look closer of what Snapcraft did, we see:

````sh
Clonage dans '/home/winael/etherpad-lite/parts/etherpad-lite/src'
````

So Snapcraft expect to build something from the `parts/etherpad-lite` folder but clone for the repo in a sub-dir, `parts/etherpad-lite/src`. So we need to indicate, in our `snpacraft.yaml` where the source is.

So edit the `snpacraft.yaml` file and add a `source-subdir: src` instruction in the `etherpad-lite` parts:

````yaml
parts:
  etherpad-lite:
    plugin: nodejs
    source: git://github.com/ether/etherpad-lite
    source-subdir: src
    stage-packages:
      - gzip
      - git
      - curl
      - python
      - libssl-dev
      - pkg-config
      - build-essential
````

Let's clean a little

````sh
$ snapcraft clean
Cleaning up for part "etherpad-lite"
Cleaning up staging area
Cleaning up snapping area
````

And let's rebuild our stage

````sh
$ snapcraft stage
````

So now, if you look into the `stage/bin` folder you could see an `etherpad-lite` entry, that is a link to the `ep_etherpad-lite/node/server.js` javascript used by nodejs

````sh
$ ls -lrt stage/bin/
total 22080
-rwxrwxr-x 2 winael winael 22607301 nov.   3 20:51 node
lrwxrwxrwx 2 winael winael       38 févr. 15 00:18 npm -> ../lib/node_modules/npm/bin/npm-cli.js
lrwxrwxrwx 2 winael winael       51 févr. 15 00:23 etherpad-lite -> ../lib/node_modules/ep_etherpad-lite/node/server.js
````


[1]: https://github.com/ether/etherpad-lite#gnulinux-and-other-unix-like-systems
[2]: https://github.com/ether/etherpad-lite/blob/develop/bin/run.sh
[3]: 