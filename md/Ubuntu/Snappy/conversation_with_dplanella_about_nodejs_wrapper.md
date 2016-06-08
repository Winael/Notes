> **David Planella @dplanella 09:24**  
> o/  
> Does anyone have experience with server snaps? I tried to get @Winael's etherpad-lite snap running, but the daemon won't start  
> https://github.com/dplanella/snappy-playpen-1/blob/master/etherpad-lite/snapcraft.yaml  
> I'm not sure how to best debug this  
> I thought that after installing the snap, the etherpad-lite-unofficial.runpad would be automatically executed and I could then point my browser to localhost:9001 and see etherpad, but I'm not sure the binary ever runs  
  
---
  
> **Winael @Winael 09:39**  
> What is the point of the wrapper ? I totally don't understand it  
> And it's quite difficult to work today, because I'm at work   
  
---
  
> **David Planella @dplanella 09:42**  
> No worries   
> The wrapper is used to call the etherpad-lite nodejs module  
> and pass it the --settings parameter  
  
---
  
> **David Planella @dplanella 09:49**  
> @Winael, the templates are in the ep_etherpad-lite nodejs module within the snap  
>  ── lib  
> │   └── node_modules  
> │       ├── ep_etherpad-lite  
> Here are the snap's contents -> http://paste.ubuntu.com/17111483/  
  
---
  
> **Winael @Winael 09:58**  
> @dplanella oh ok... the etherpad-lite-src is not necessary  but I didn't find scripts from https://github.com/ether/etherpad-lite/tree/develop/bin in your snap content  
  
---
  
> **Winael @Winael 10:05**  
> @dplanella in your runpadfile i read exec $SNAP/bin/etherpad-lite --settings $PWD/etc/settings.json but if i take a look at the doc I see ExecStart=/usr/bin/nodejs /opt/etherpad/node_modules/ep_etherpad-lite/node/server.jsthat could be translate to $SNAP/bin/nodejs $SNAP/lib/node_modules/ep_etherpad-lite/node/server.js I suppose.  
  
---
  
> **David Planella @dplanella 10:05**  
> yeah, that's what the wrapper ultimately does  
> it's just that there is quite a lot of indirection  
  
---
  
> **Winael @Winael 10:05**  
> SO I think I have a lack of culture but I don't understand how you create runpad and the makefile.... I really miss a step  
  
---
  
> **David Planella @dplanella 10:06**  
> They are two different things  
> The Makefile is the easy part  
> It is simply used to a) create an additional npm config file and b) to install the wrapper  
  
---
  
> **Winael @Winael 10:08**  
> but the node js plugin can't do it by it self ?  
> So typically, if i want to build another nodejs app, I need to create a Makefile like this ?  
  
---
  
> **David Planella @dplanella 10:09**  
> so when the wrapper-and-config part is built and installed, it creates the npmrc file and puts the runpad wrapper in the final place it will be in the other snap  
> No, generally you wouldn't need it, it's simply because the additional config file and the additional --settings switch you need to pass in the wrapper  
> However, the thruth is that node apps generally don't follow a standard for building and installing  
  
---
  
> **David Planella @dplanella 10:11**  
> So in practice you end up adding things (generally parts or plugins) to your snapcraft files to build them  
  
---
  
> **David Planella @dplanella 10:15**  
> @Winael and on the question on the wrapper itself, if you install the snap, you can follow what all the wrappers ultimately execute:  
>  command-etherpad-lite.wrapper -> bin/runpad -> bin/etherpad-lite # (which is a symlink to ../lib/node_modules/ep_etherpad-lite/node/server.js)  
> which ultimately leads to the server.js file you were pointing at above  
> and I think command-etherpad-lite.wrapper is created by snapd for you automatically when you install a snap, but I'm not an expert there  
  
---
  
> **Winael @Winael 10:18**  
> @dplanella ah ok...  
> so runpad exec etherpad-lite with the param files, make build it with the variable env of the snap,  
> So in fact, I can't take an install documentation and transpose it to build a snap ?  
  
---
  
> **David Planella @dplanella 10:29**  
> yes, runpad is simply needed to exec bin/etherpad-litewith parameters. If parameters were not needed, then we could get rid of the wrapper and bin/etherpad-lite would be executed directly  
> the Makefile is only added there to actually install the runpad wrapper  
>  
> > So in fact, I can't take an install documentation and transpose it to build a snap ?  
>  
> @Winael I'm not sure I understand the question ^, could you clarify?
