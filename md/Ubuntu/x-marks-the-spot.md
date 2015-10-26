---
file: x-marks-the-spot.md
title: "X marque le lieu"
description: 'Mark Suttleworth - Blog post about X name'
author: Mark Shuttleworth
translation: Winael
date: 2015-10-26
category: Ubuntu
tags: Ubuntu,Ubuntu operating system,tablet,smartphone,phone,convergence,lxc,lxd,Snappy,MaaS,Juju
viewport: 'width=device-width, initial-scale=1'
---

<meta http-equiv='Content-Type' content='text/html; charset=utf-8' />

What a great Wily it’s been, and for those of you who live on the latest release and haven’t already updated, the bits are baked and looking great. You can jump the queue if you know where to look while we spin up the extra servers needed for IMG and ISO downloads :)

Utopic, Vivid and Wily have been three intense releases, packed with innovation, and now we intend to bring all of those threads together for our Long Term Support release due out in April 2016.

![][1]

**LXD is the world’s fastest hypervisor, led by Canonical, a pure-container way to run Linux guests on Linux hosts.** If you haven’t yet played with LXD (a.k.a LXC 2.0-b1) it will blow you away.  It will certainly transform your expectations of virtualisation, from slow-and-hard to amazingly light and fast. Imagine getting a full machine running any Linux you like, as a container on your laptop, in less than a second. For me, personally, it has become a fun way to clean up my build processes, spinning up a container on demand to make sure I always build in a fresh filesystem.

Snappy packages have transactional updates with rollback
Snappy Packaging System

**Snappy is the world’s most secure packaging system**, delivering crisp and transaction updates with rollback for both applications and the system, from phone to appliance. We’re using snappy on high-end switches and flying wonder-machines, on raspberry pi’s and massive clouds. Ubuntu Core is the all-snappy minimal server, and Ubuntu Personal will be the all-snappy phone / tablet / pc. With a snap you get to publish exactly the software you want to your device, and update it instantly over the air, just like we do the Ubuntu Phone. Snappy packages are automatically confined to ensure that a bug in one app doesn’t put your data elsewhere at risk. Amazing work, amazing team, amazing community!

MAAS is your physical cloud
Metal as a Service

MAAS is your physical cloud, with bare-metal machines on demand, supporting Ubuntu, CentOS and Windows. Drive your data centre from a single dashboard, bond network interfaces, raid your disks and rock the cloud generation. Led by Canonical, loved by the world leaders of big, and really big, deployments. MAAS gives you high availability DNS, DHCP, PXE and other critical infrastructure, for huge and dynamic data centres. Also pretty fun to run at home.

Juju is… model-driven application orchestration, that lets communities define how big topological apps like Hadoop and OpenStack map onto the cloud of your choice. The fastest way to find the fastest way to spin those applications into the cloud you prefer. With traditional configuration managers like Puppet now also saying that model-driven approaches are the way to the future, I’m very excited to see the kinds of problems that huge enterprises are starting to solve with Juju, and equally excited to see start-ups using Juju to speed their path to adoption. Here’s the Hadoop, Spark, IPython Notebook coolness I deployed live on stage at Apache Hadoopcon this month:

Juju model of Apache Hadoop with Spark and IPython Notebook
Apache Hadoop, Spark, IPython modelled with Juju

All of these are coming together beautifully, making Ubuntu the fastest path to magic of all sorts. And that magic will go by the codename… xenial xerus!

What fortunate timing that our next LTS should be X, because “xenial” means “friendly relations between hosts and guests”, and given all the amazing work going into LXD and KVM for Ubuntu OpenStack, and beyond that the interoperability of Ubuntu OpenStack with hypervisors of all sorts, it seems like a perfect fit.

And Xerus, the African ground squirrels, are among the most social animals in my home country. They thrive in the desert, they live in small, agile, social groups that get along unusually well with their neighbours (for most mammals, neighbours are a source of bloody competition, for Xerus, hey, collaboration is cool). They are fast, feisty, friendly and known for their enormous… courage. That sounds just about right. With great… courage… comes great opportunity!

[1]: http://assets.ubuntu.com/sites/ubuntu/1533/u/img/homepage/lxd_takeover.png
