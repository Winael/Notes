---
file: openstack-summit-tokyo-canonical-resume.md
title: Résumé de Canonical de l'OpenStack Summit Tokyo
author: Bill Bauman
translation: Winael
date: 2015-11-01
category: OpenStack
tags: openstack
status: to_translate
---

# Day One

![OpenStack Tokyo][1]

Yesterday was our first full day here at OpenStack Summit Tokyo, and the themes seemed pretty clear. Increased focus on applications and containers – containers – containers. The best part about that is how validating it feels. We’ve been focused on improving the usability of containers for several years now, and that’s been realized in LXD – the container hypervisor. Of course, applications – scalable, intelligent, hands-off and dynamic, well, Juju’s been doing that for years, and is by far the most mature, modern application deployment and modeling tool.

There was a great session on OpenStack installers, and it touched on upgrades, as well. The cool part was that Juju got high praise for its maturity, stability, and ability to upgrade consistently. And that’s just for OpenStack. Juju does so much more than just that. It deploys and upgrades OpenStack, but what’s really cool is how it manages all the applications on top of it. Seriously, if you haven’t seen Juju, check it out at http://jujucharms.com. It’s way cool, and we’ll be talking about it more this week.

Another theme that’s not specific to this week but has been building momentum from one summit to another, is the inclusion of more than just developers and development cycles around OpenStack. There are sessions here in Tokyo at all levels. There are business-focused sessions, extremely technical how-to sessions for engineers and ops folks, and best practices sessions, like the one Canonical’s Billy Olsen gave, around everything you should know and keep in mind during an OpenStack upgrade.

Are you here in Tokyo this week? Come visit us in the Marketplace at booth S3, in the back room on the left side. We’d love to hear about your take on the summit, what you’re doing with OpenStack, and how we can help you. If you’re not here, subscribe to Insights below and follow along.

# Day Two

![OpenStack Summit Tokyo 2015 Canonical Booth800][20]

The keynote sessions that kicked off the second day of OpenStack Summit Tokyo continued the theme of containers, but got a little deeper into the business drivers, and the purposes of why we’re building scalable clouds. Resonant Japan talked about accelerating business operations, cost reductions, and supporting the scalability of the third-largest portal in Japan – Goo. Scott Crenshaw, SVP at Rackspace, talked about how containers increase performance, offer simplicity through their new Carina Clusters offering, and bring better economics to clouds at scale.

So I want to share why I’m so excited to hear what our colleagues and partners are talking about. The night before the summit started, Mark Shuttleworth brought together the Canonical team to talk about the driving forces behind everything we’re working on. The centers of gravity for what we do are Economics, Simplicity, Scale, and Performance. That’s exactly what our colleagues said in their keynotes to kick off day 2, and Canonical is packaging those concepts in software you can deploy in your own environment.

It’s not an accident that Ubuntu is the majority platform for all OpenStack deployments. The economics, and the ease of use that our supporting tools like MaaS, OpenStack Autopilot (more on this tomorrow), and Juju (ever more on Juju tomorrow, too!) provide are really unmatched. If you use any of our tools, or even just Ubuntu, I think you see the simplicity is in the forefront. Performance resonates throughout, just consider the LXD announcement from the previous OpenStack Summit in Vancouver, BC – 14x density, reduced latency, increased throughput, over KVM.

The other theme we got out of yesterday was about networking. The network is finally seeing its big day. Neutron had more commits to it than Nova. The SDN vendors, Canonical partners as well, are all seeing increased uptake in their differentiated offerings. Canonical will be talking about a new way of looking at the underlying construct of sotware defined networking in day 3 sessions, so check in tomorrow for our day 3 update for more on networking, and more on the four centers of gravity that are making Ubuntu OpenStack so consumable and usable.

# Day Three

![Mark_Shuttleworth_Keynote_Tokyo][30]

Day three of the summit didn’t feature highlighted keynote sessions like days one and two. But it did have an entire Canonical track schedule, which kicked off with Mark Shuttleworth talking about why we build the tools and features we do, what’s new, and some of what’s to come. The centers of gravity I mentioned yesterday anchor everything, and Mark’s message yesterday spoke to why – OpenStack for everyone.

## No headcount, no consultants, no problem

OpenStack continues to evolve to be more than a very exclusive, specialist, cluster to something everyone can run for themselves. The driver behind all of this is economics. OpenStack makes the private cloud possible and rational. What Mark’s saying is that as we continue to scale out and grow compute capacity, the underlying solution must have a scalable economic model, or it’s not rational to pursue it. The economics are as important as the technology itself.

Mark also talked about the importance of the changes to the governance of the core projects and how important that is to Canonical. There are so many supporting projects now that it’s important we have a definitive focus on the compute, networking, and storage projects. Everything Mark talked about fit into the theme of the week, and led into some new product introductions.

In Vancouver Mark demonstrated the OpenStack Autopilot. Yesterday, he announced the GA of Autopilot for the 10th of November. The OpenStack Autopilot brings together everything we’ve learned from very large, very small, very interesting OS deployments and allows us to distill our insight into code that everyone can use. This is really a different approach than the high touch, highly customized installations of OpenStack that are so popular with some distributions. We think that the consumability and usability of OpenStack is more important than corner case features. This doesn’t mean we can’t do both, but for the economics to really work, the intelligence needs to be built into the software, not just the people.

With Autopilot, Canonical’s “OpenStack Reference Architecture” is not a finite plan, but rather intelligently, automatically built, based on the hardware that’s there. And it dynamically will update itself as you add additional hardware.

Mark also touched on the networking theme that’s been pervasive this week, but, he talked about it from a slightly different perspective. He talked about how Canonical is using Snappy, a read-only, small footprint Ubuntu as the base for a new generation of network switches. The thought here is that our SDN partners can be freed up to focus on networking. We’ll handle the drivers, the kernel, the patching, the security. Basically, we do what we do best, and they do what they do best.

The decoupling of the network control layer (the SDN partner solution) from the operating system also makes for increased portability of an SDN solution. If the SDN vendor doesn’t have to write and maintain firmware and hardware-specific drivers for each build of their software, then it can run literally anywhere that Canonical has validated Snappy. Mark announced three partners already in his talk yesterday – Quanta Cloud Technology, Agema, Penguin Computing.

Everything happening at OpenStack Summit this week is pushing toward ease of use, faster deployments, machine intelligence in our private clouds. It was really cool to hear Mark talk about all the ways that Canonical is helping support that in the OpenStack community.

If you haven’t had a chance to try out Ubuntu OpenStack yet, or want some help getting going, you should consider BootStack, an inexpensive, privately managed OpenStack solution. Check it out here.



[1]: https://insights.ubuntu.com/wp-content/uploads/f67e/20151027_172000.png
[20]: https://insights.ubuntu.com/wp-content/uploads/20dd/OpenStack-Summit-Tokyo-2015-Canonical-Booth800.jpg
[30]: https://insights.ubuntu.com/wp-content/uploads/0d6d/Mark_Shuttleworth_Keynote_Tokyo.jpg
