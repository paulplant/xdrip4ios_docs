![](.\img\xdrip4ios.jpg)

# Introduction

**xDrip4iOS** (also known as **"xDrip for iOS"** or **"xdripswift"**) is an open-source application to display real time blood glucose data.

It is able to connect as a **Master** device to various types of Continuous Glucose Monitor systems and display their values on the screen. This is the main way that most people (usually patients with Type 1 Diabetes) will use the app.

It is also able to act as a **Follower** device and pull remote CGM data from [Nightscout](https://nightscout.github.io/). This is a great way for parents and care-givers to be able to remotely monitor loved ones and patients.

!!!warning "IMPORTANT"
    Please note that **xDrip4iOS** is not related to the **xDrip+** project for **Android**.

    For help and information about the **xDrip+** project for Android, please see [here](https://github.com/NightscoutFoundation/xDrip)

## What Do I Need?

To run xDrip4iOS you will firstly need an iPhone 7 or newer running minimum iOS13.

To work as a **Master** device, you will need to have a compatible CGM system (see below). If you want to share your CGM data with Nightscout, then you will also need a working internet connection.

To work as a **Follower** device, you don't need anything except an internet connection and a working Nightscout site from where to follow the master device.

That's it. Nothing else is needed.

!!!warning "IMPORTANT"
    **Before using xDrip4iOS**, it is important to understand several points:

    - This is an open-source, community-based project and is not supported by any company
    - It is not officially approved or regulated for diabetes therapy and/or treatment in any way whatsoever
    
    **You must understand that you take full responsibility for using this software and you agree to do so at your own risk.**

## Compatible Sensors/Transmitters

xDrip4iOS is compatible with many FreeStyle Libre sensors and also certain Dexcom sensors/transmitters.

#### FreeStyle Libre 1 *(European 14 day)*

Transmitter Type &nbsp;&nbsp;&nbsp;| Firmware Version &nbsp;&nbsp;&nbsp;| Compatible? &nbsp;&nbsp;&nbsp;
:-------------- |:------------- | :-----------
MiaoMiao 1        | All | **Yes** 
MiaoMiao 2          | All  | **Yes** 
 Bubble | All | **Yes** 
 Atom | All | **Yes** 
 GNSentry | All | **Yes** 

</br>
#### FreeStyle Libre 2 *(European 14 day)*

| Transmitter Type &nbsp;&nbsp;&nbsp;                 | Firmware Version &nbsp;&nbsp;&nbsp; | Compatible? &nbsp;&nbsp;&nbsp; |
| :-------------------------------------------------- | :---------------------------------- | :----------------------------- |
| Direct Bluetooth (no transmitter)&nbsp;&nbsp;&nbsp; | -                                 | **Yes**                        |
| MiaoMiao 1                                          | >= 39                           | **Yes** *(1)*             |
| MiaoMiao 2                                          | >= 7                             | **Yes** *(1)*          |
| Bubble                                              | All                              | **Yes**                        |
| Atom                                                | All                              | **Yes**                        |
| GNSentry                                            | -                                | No                             |

</br> 
 **(1)** The MiaoMiao firmware can be upgraded, if needed, using Tomato App </br>
</br>

#### FreeStyle Libre 1/2 US *(10 day, 14 day & Libre 2)*, Libre Pro 
- Not compatible

#### Dexcom G4/G5
- FullyCompatible

#### Dexcom G6

| Transmitter Serial Number &nbsp;&nbsp;&nbsp;        | Firmware/ Version &nbsp;&nbsp;&nbsp; | Compatible? &nbsp;&nbsp;&nbsp; |
| :-------------------------------------------------- | :----------------------------------- | :----------------------------- |
| 80xxxx                                              | All                                  | **Yes**                        |
| 81**x**xxx (3rd digit is usually a **number**)      | <= x.x.x.25                          | **Yes**                        |
| 81**x**xxx (3rd digit is usually a **letter**)      | \>= x.x.x.27                         | No                             |
| 8Gxxxx, 8Hxxxx, 8Jxxxx ... etc *("Firefly")* &nbsp; | -                                    | No                             |

</br>


## Who Can Help Me?

The main public support group for all support is the xDrip4iOS group on [Facebook](https://www.facebook.com/groups/853994615056838).

You can also find all source code, technical information and register issues in our  [Github repository](https://github.com/JohanDegraeve/xdripswift).
</br>

## Development History

This project was started back in 2017 by **Johan Degraeve**. His idea was to port the original xDrip algorithm to iOS.

The original project he created was called **xdripiosreader**. This was later re-written in 2019 into native swift code and renamed to **xdripswift**.

In 2020, the user interface was overhauled, more features were added and the project was renamed to **xDrip4iOS**.

## How Can I Help?

You'll find the source repository for this documentation [here](https://github.com/xxxxxxx). Please don't hesitate to improve or correct anything you see and create a pull request!

You're also welcome to contribute or report any error, unclear explanation, typo, broken link etc by going to Github and opening an [issue](https://github.com/JohanDegraeve/xdripswift/issues).