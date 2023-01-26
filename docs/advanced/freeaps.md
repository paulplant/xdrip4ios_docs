# FreeAPS (Loop) Integration

FreeAPS used to be the only way to use xDrip4iOS as an offline cgm data source for Loop, but since the release of Loop 3 a new branch called [main_lnl_patches](https://www.loopandlearn.org/github-lnl-patches/) has been created by Loop And Learn which also supports using xDrip4iOS as an offline cgm data source for Loop (as well as support for Glucose Direct and the integration of the CustomTypeOne patch which adds more features to Loop 3). Because Loop and Learn has shifted their focus to Loop 3 and will only perform minor maintainance on FreeAPS, it is highly reccommended that users of FreeAPS switch to this branch of Loop 3 instead.

___
## What is FreeAPS (Loop)?

**Loop** is an **Artificial Pancreas System** (APS) written for the iPhone.

An APS works by reading blood glucose values, predicting/calculating the insulin requirement and automatically adjusting a user's insulin pump with the aim of keeping the user within their target blood glucose range.

[FreeAPS](https://www.loopandlearn.org/freeapsdoc/) is a fork of the [Loop](https://loopkit.github.io/loopdocs/) project. This fork was originally developed by **Ivan Valkou**. His repository was frozen last spring. To support the users of the FreeAPS fork, maintenance was taken over by the Loop and Learn mentors. Only minor maintenence will be performed, though, so users are highly encouraged to switch to the [main_lnl_patches](https://www.loopandlearn.org/github-lnl-patches/) branch of Loop 3 which also supports xDrip4iOS as an offline cgm source.

!!!info "FreeAPS vs FreeAPS X??"
    This could get confusing, so pay attention:

       - Ivan's original **FreeAPS** project is based on **Loop** and is what we are discussing on this page<br /><br />
       - Ivan's newer **FreeAPS X** project is based on **OpenAPS**. It is a different system and is discussed [here](freeapsx.md)<br /><br />
  
The main difference between Loop and FreeAPS is that FreeAPS has a different methodology than Loop (v2.2.6 or later) for delivering extra insulin via micro-boluses and adjusting basal rates. FreeAPS is more customizable and flexible.

For FreeAPS, v2.2 (202) or later, support is included for xDrip4iOS built off the work of and in the collaboration with Aleksandar Obucina and based upon an [xdrip client](https://github.com/julian-groen/xdrip-client-swift) from Julien Groen.

Whereas Loop will only work with compatible Dexcom or Medtronic pump-connected sensors, FreeAPS also contains a Nightscout client which can be used to pull glucose data from the user's Nightscout site (this requires internet access via WiFi or cell coverage), or via apps (such as Spike) that have an internal http server that mimics a Nightscout server. 

Using on-the-local-phone CGM access using Dexcom or xDrip4iOS (Dexcom G4/5/6 + Libre with some [limitations](../index.md#compatible-sensors)) does not require internet access and is thus a preferred method for looping.

Important: The Testflight version of xDrip4iOS **cannot** be used with FreeAPS. You must build xDrip4iOS from source.
___
## How do I install FreeAPS (Loop)?

Instructions for installing FreeAPS can be found at [Loop and Learn](https://www.loopandlearn.org/freeapsdoc/).

Remember that xDrip4iOS is a separate app and must be [built from source](../install/build.md) in order to successfully interface with FreeAPS.

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
