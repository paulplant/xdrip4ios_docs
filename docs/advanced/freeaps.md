# FreeAPS (Loop) Integration

xDrip4iOS can be used as an offline CGM data source for the FreeAPS fork of Loop

___
## What is FreeAPS (Loop)?

**Loop** is an **Artificial Pancreas System** (APS) written for the iPhone.

An APS works by reading blood glucose values, predicting/calculating the insulin requirement and automatically adjusting a user's insulin pump with the aim of keeping the user within their target blood glucose range.

[FreeAPS](https://github.com/ivalkou/LoopWorkspace) is a fork of the [Loop](https://loopkit.github.io/loopdocs/) project developed and maintained by **Ivan Valkou**.

!!!info "FreeAPS vs FreeAPS X??"
    This could get confusing, so pay attention:

       - Ivan's original **FreeAPS** project is based on **Loop** and is what we are discussing on this page<br /><br />
       - Ivan's newer **FreeAPS X** project is based on **OpenAPS**. It is a different system and is discussed [here](freeapsx.md)<br /><br />
  
The main difference between Loop and FreeAPS is that FreeAPS is able to administer insulin delivery via micro-boluses instead of adjusting basal rates. Although Loop also now has an autobolus branch which is similar, FreeAPS is much more customizable and flexible.

It is important to note that the app developer has decided to halt all active development on FreeAPS in order to concentrate all efforts on his new FreeAPS X project. Collaborators are encouraged to participate with the maintenance of the fork.

Whereas Loop will only work with compatible Dexcom or Medtronic pump-connected sensors, FreeAPS also contains a Nightscout client which can be used to pull glucose data from the user's Nightscout site, or via apps (such as Spike) that have an internal http server that mimics a Nightscout server. 

Pulling data from the cloud, or using http servers on iOS, are potentially unstable options for an APS (although they will generally work well most times).

**Aleksandar Obucina** has created a fork of Ivan's FreeASP (Loop). This includes an [xdrip client](https://github.com/julian-groen/xdrip-client-swift) written in Swift by **Julien Groen**. This modified version of FreeAPS has xDrip4iOS as a CGM option and will pull glucose data directly offline from xDrip4iOS without needing to use any intermediate services.

It is necessary to clone, build and install Aleksandar's fork of FreeAPS and then do the same with the master branch of xDrip4iOS.

Important: The Testflight version of xDrip4iOS **cannot** be used with FreeAPS.
___
## How do I install FreeAPS (Loop)?

Aleks' Github repository is [here](https://github.com/alekst1d/LoopWorkspace).

In LoopDocs there is a nice page about cloning and building workspace files [here](https://loopkit.github.io/loopdocs/build/loopworkspace/).

Please read the above page and ensure your Mac is fully updated (both MacOS and Xcode) and Xcode Command Line tools/Git are installed before proceeding.
___
### Clone the LoopWorkspace
First we need to create a folder where we will clone the source code and build the project.

We recommened creating a folder in your Documents called "**FreeAPS**".

Open **Terminal** on your Mac and type in the following to change to your Documents folder:

*(You can copy and paste the below text, one line at a time, pressing return after pasting each line)*

    cd documents

Create the new folder:

    mkdir freeaps

Change into the newly created folder:

    cd freeaps

We will now issue a Git command to clone (download) the current version of Aleks' repository into your new folder:

    git clone --branch=freeaps --recurse-submodules https://github.com/alekst1d/LoopWorkspace

This will create a new folder called LoopWorkspace containing the source code. 

You should now navigate into this new folder:

    cd LoopWorkspace

We will now open the workspace file in Xcode by typing the following:

    xed .
___
### Sign the Targets

As per a normal Loop build, you will need to sign the four targets using your Development Team.

Signing will automatically set the Bundle Identifier for your app. You can change this, but be aware that it will then install a completely new FreeAPS app. It's better to just leave it as is.
___
### App Group

Please do not modify the App Groups at all. This is important to ensure integration with xDrip4iOS.

___
## How do I install xDrip4iOS?

You need to follow the [Build From Source](../install/build.md) instructions.


The common LoopKit app group is already written into the standard project file in xDrip4iOS so no need to touch anything.

___
## Operation

The operation of both FreeAPS (Loop) and xDrip4iOS is the same. The only thing needed is to add a CGM in FreeAPS and chose "xDrip4iOS".

This will tell FreeAPS to look for glucose data in the shared app group via Julien's xdrip client.






</br>