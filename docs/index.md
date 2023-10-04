![](.\img\xdrip4ios.jpg)

# Introduction

**xDrip4iOS** (also known as **"xDrip for iOS"** or **"xdripswift"**) is an open-source application to display real time blood glucose data.

<img src=".\img\xDrip4iOS_env.png" style="zoom:67%;" />

It is able to connect as a **Master** device to various types of Continuous Glucose Monitor systems and display their values on the screen. This is the main way that most people (usually patients with Type 1 Diabetes) will use the app.

It is also able to act as a **Follower** device and pull remote CGM data from [Nightscout](https://nightscout.github.io/). This is a great way for parents and care-givers to be able to remotely monitor loved ones and patients.

!!!info "FOR XDRIP+ USERS"
    Please note that **xDrip4iOS** is not related to the **xDrip+** project for **Android**.

    For help and information about the **xDrip+** project for Android, please see [here](https://github.com/NightscoutFoundation/xDrip) or look on [Facebook](https://www.facebook.com/groups/xDripG5).

___
## What Do I Need?

To run xDrip4iOS you will firstly need an iPhone 7 or newer running minimum iOS15.

To work as a **Master** device, you will need to have a compatible CGM system (see below). If you want to share your CGM data with Nightscout, then you will also need a working internet connection.

To work as a **Follower** device, you don't need anything except an internet connection and a working Nightscout site from where to follow the master device.

That's it. Nothing else is needed.

!!!warning "IMPORTANT"
    **Before using xDrip4iOS**, it is important to understand several points:

    - This is an open-source, community-based project and is not supported by any company
    - It is not officially approved or regulated for diabetes therapy and/or treatment in any way whatsoever
    
    **You must understand that you take full responsibility for using this software and you agree to do so at your own risk.**

___
## Compatible Sensors

xDrip4iOS is compatible many different Libre sensors and Dexcom sensors/transmitters.

### Libre 
**Libre 1 European** *(14 day)*

| Transmitter Type &nbsp;&nbsp;&nbsp;| Firmware Version &nbsp;&nbsp;&nbsp;| Compatible? &nbsp;&nbsp;&nbsp; |
|:-------------- |:------------- | :----------- |
| MiaoMiao 1, 2, 3  | All | **<span style="color:green">Yes</span>** |
| Bubble, Bubble mini | All | **<span style="color:green">Yes</span>** |
| Atom | All | **<span style="color:green">Yes</span>** |
| GNSentry | All | **<span style="color:green">Yes</span>** |

</br>

**Libre 1 US**  *(14 day)*

| Transmitter Type &nbsp;&nbsp;&nbsp; | Firmware Version &nbsp;&nbsp;&nbsp; | Compatible? &nbsp;&nbsp;&nbsp; |
| :------------------------------------ | :---------------------------------- | :----------------------------- |
| Direct Bluetooth (no transmitter)&nbsp;&nbsp;&nbsp; | -                                 | **<span style="color:red">No</span>** |
| MiaoMiao 1                                          | >= 39                           | **<span style="color:green">Yes</span>** *(1)*             |
| MiaoMiao 2                                          | >= 7                             | **<span style="color:green">Yes</span>** *(1)*          |
| Miaomiao 3 | - | **<span style="color:green">Yes</span>** *(1)* |
| Bubble, Bubble mini                               | All                              | **<span style="color:green">Yes</span>**                        |
| Atom                                                | All                              | **<span style="color:green">Yes</span>**                        |
| GNSentry                                            | -                                | **<span style="color:red">No</span>**                             |

 *(1) The MiaoMiao firmware can be upgraded, if needed, using Tomato App*
</br>

**Libre 2 European** *(14 day)*

| Transmitter Type &nbsp;&nbsp;&nbsp; | Firmware Version &nbsp;&nbsp;&nbsp; | Compatible? &nbsp;&nbsp;&nbsp; |
| :------------------------------------ | :---------------------------------- | :----------------------------- |
| Direct Bluetooth (no transmitter)&nbsp;&nbsp;&nbsp; | -                                 | **<span style="color:green">Yes</span>**  |
| MiaoMiao 1                                          | >= 39                           | **<span style="color:green">Yes</span>** *(1)*             |
| MiaoMiao 2                                          | >= 7                             | **<span style="color:green">Yes</span>** *(1)*          |
| Miaomiao 3 | - | **<span style="color:green">Yes</span>** *(1)* |
| Bubble, Bubble mini                               | All                              | **<span style="color:green">Yes</span>**/**<span style="color:red">No</span>** *(2)*                       |
| Atom                                                | All                              | **<span style="color:green">Yes</span>**                        |
| GNSentry                                            | -                                | **<span style="color:red">No</span>**                             |

 *(1) The MiaoMiao firmware can be upgraded, if needed, using Tomato App*
 </br>
 *(2) Bubble and Bubble Mini transmitters are not currently compatible with xDrip4iOS if using the newer "C5" Libre 2 EU sensors*
</br> </br> 

**Libre 2 US/Canadian/Australian**

- **<span style="color:red">Not compatible at the current time</span>**
</br>  

**Libre Pro, Libre H**

- **<span style="color:red">Not compatible at the current time</span>**
</br>  

**Libre 3**

- **<span style="color:red">Not compatible at the current time</span>**
</br>  

___
### Dexcom 

**Dexcom G4** *(1)* **/ G5** <span style="color:orange"><--- (Obsolete)</span>

- **<span style="color:green">Fully compatible</span>** with a bridge/Wixel device and using raw data mode.
</br> 

**Dexcom G5** <span style="color:orange"><--- (Obsolete)</span>

- **<span style="color:green">Fully compatible</span>** using raw mode.
</br> 

**Dexcom G6**

- **<span style="color:green">Fully compatible</span>** using native mode.

All G6 transmitters (including older pre-firefly 80xxxx/81xxxx transmitters) will work in **native mode** using the algorithm inside the transmitter. This means that xDrip4iOS will have a 2 hour warm-up, a factory 10 day sensor expiry and a 90-110 day transmitter life. 

The sensors can be started using the sensor code on the label and can be calibrated from inside the xDrip4iOS app.

You can connect to the G6 transmitters in two ways:

1. Directly to the transmitter using xDrip4iOS and *without using the Dexcom app*
2. Indirectly to the transmitter using xDrip4iOS and the Dexcom app in parallel by enabling "Read from Dexcom app" mode.

If using a modified G6 **Anubis** transmitter, the Anubis-specific limits (50 minute warm-up, 60 day sensor expiry, 180 day transmitter expiry, resetable) all apply. For more information about the Anubis project, please see the [Facebook group](https://www.facebook.com/groups/310545804061135).
</br> 

**Dexcom ONE**

- **<span style="color:green">Partially compatible</span>** using native mode with **"Read from Dexcom app" enabled** (see below).
 
Dexcom One transmitters  will work in **native mode** using the algorithm inside the transmitter. This means that xDrip4iOS will have a 2 hour warm-up, a factory 10 day sensor expiry and a 90-110 day transmitter life. 

The sensors can be started using the sensor code on the label.

Note that One transmitters with a transmitter ID **starting with C** (Cxxxxx) can only be used with "Read from Dexcom App" enabled. They also **cannot be calibrated** from within xDrip4iOS.
</br> 
</br> 

**"Read from Dexcom App" Mode**
</br> 
If you need to use the official Dexcom app to upload data to Dexcom Share or Clarity, you can set xDrip4iOS to "Read from Dexcom App" mode. 

In this mode, the main connection between the transmitter and your iPhone is handled by the Dexcom app. xDrip4iOS will simply receive a copy of the transmitted data and process it. This allows you to use xDrip4iOS for all features (alarms, graphs, statistics, Nightscout, Watch app etc) without needing to stop using the official app.
</br> 

___
## Where Can I Get Help?

The **official public group** for all technical support is the **xDrip4iOS** group on [Facebook](https://www.facebook.com/groups/853994615056838). Feel free to join the group, ask questions and participate.

Please **do not** send e-mails or private messages to the development team requesting general/personal help with the app. Help of this type is only offered in the xDrip4iOS Facebook group.

You can also find all source code, technical information and register issues in our  [GitHub repository](https://github.com/JohanDegraeve/xdripswift).

All bug reports should be carefully verified and raised in GitHub as an issues.

Again, do not raise GitHub issues if you are just new to the app and are looking for technical help or assume something isn't working - please read these instructions and visit the Facebook group for help in this case.
</br>

___
## Development History

This project was started back in 2017 by **Johan Degraeve**. His idea was to port the original [xDrip](http://stephenblackwasalreadytaken.github.io/xDrip/) algorithm to iOS.

The original project he created was called **[xdripiosreader](https://github.com/JohanDegraeve/iosxdripreader)**. This was later re-written in 2019 into native swift code and renamed to **xdripswift**.

In 2020, the user interface was overhauled, more features were added and the user-facing project was renamed to **xDrip4iOS**.

___
## How Can I Get Involved?

You'll find the Github source repository for this documentation [here](https://github.com/paulplant/xdrip4ios_docs). Please don't hesitate to improve or correct anything you see and create a pull request!

You're also welcome to contribute or report any documentation error, unclear explanation, typo, broken link etc by going to Github and opening an [issue](https://github.com/paulplant/xdrip4ios_docs/issues).