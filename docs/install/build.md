# How to Build xDrip4iOS using Xcode

Although for most users, the recommended method for installing xDrip4iOS is to just use [Testflight](testflight.md), many users will want to build directly from source. If so, this page is for you!

![Xcode](img/build_xcode.png)

xDrip4iOS is an open-source project and is released under the [**GNU General Public License v3.0**](https://github.com/JohanDegraeve/xdripswift/blob/master/LICENSE).

Most users that decide to build from source will be people who are interested in collaborating in the development of the project or users who are used to DIY solutions (such as Loop or FreeAPS), have a valid Apple Developer license/account and are comfortable working with Xcode.

Although **xDrip4iOS** is the common *public* name for the application, the actual Github project name is **xdripswift** and you will often so it referred to as this in the following documentation.

The main project repository is [here](https://github.com/JohanDegraeve/xdripswift)

Ready? So then let's begin. Here are some of the things that you'll need before you're able to build and install the app:

- A Mac computer (iMac, MacBook etc).
- A valid Apple Developer account/license. If not, you could theoretically use a free Apple ID to sign the app with but you will have to remove Healthkit and NFC integration capabilities as well as needing to re-sign the app every 7 days. ***It's really not worth considering this path if you do not have a current Apple Developer account***
- Xcode installed. This can be done from the App Store on your Mac.
- Git installed. If you're unsure how to do this, please follow the guide [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
- A compatible cable to connect your iPhone (Lightning port) to your Mac (USB-C or USB-A as needed)
  
It is recommeneded to always use the latest versions of MacOS and Xcode. Your iPhone should ideally also be using the latest version of iOS.
___
### Apple Developer Account

To be able to build and run xDrip4iOS without restrictions on your personal devices, you will ideally need an Apple Developer Account. This is a paid account (around 100 EUR/USD per year) which gives you full access to Apple development tools and documentation, together with the ability to self-sign your own apps (or submit them to Testflight or App Store if you wanted).

More information at the [Apple Developer](https://developer.apple.com) website.

___
### Install the Cocoa Pods Framework to your Mac

If this is the first time that you have built xDrip4iOS on your Mac, then you will need to install a set of frameworks called CocoaPods. If you have previously installed CocoaPods, you can skip this step.

!!!info "APPLE "M1" PROCESSOR?"
    In this step, the process will change slightly depending on the type of Mac you are using. You will be using either an Intel-based or M1-based Mac.

    - The newer Mac Mini, MacBook Air or MacBook Pro (2020-2021) will generally have the new M1 processor (aka *Apple Silicon*)
    - Most older Macs (<2020) will be running Intel processesors and will not need the following step to be carried out
  
    If you are one of these newer M1 Macs, then you **must perform** the following steps before trying to install the Cocoapods framework.
    
    Firslty, make sure you run Terminal using *Rosetta* (this is an Apple tool that allows you to *translate* older applications to run on the newer M1 architecture):

    - Right-click on Terminal in Finder
    - Click "Get Info"
    - Select "Open with Rosetta"
    - Clikc "OK"
  
    Then, open Terminal and run the following command to install **ffi**:

    **sudo gem install ffi**

    Once successfully installed, you should now be able to continue as per the Intel instructions below


To install the Cocoapods framework to your Mac, please enter the following command:

    sudo gem install cocoapods

Note the use of "**sudo**" here to elevate the permissions to allow installation at a system level. If asked for your password, use the admin password that you use to log into your Mac (this is generally just your user password).

You should get an "OK" message confirming successfull installation. 


### Clone the xdripswift project

Good job for getting to here. Now it's time to grab a copy of the source code from Github and build the project.

You should open Terminal, navigate into your Documents folder (or wherever you prefer) and run the following command to clone the xDrip4iOS project:

    git clone --branch=master --recurse-submodules https://github.com/JohanDegraeve/xdripswift

This will create a new folder called xdripswift and it will copy all needed code into it. Once completed we should navigate into this folder:

    cd xdripswift

### Install Cocoa Pods Dependencies

Earlier we installed the full Cocoa Pods framework onto your system. Now we will go into the cloned project folder and install the individual project dependencies there:

    pod install

Again, you will see some activity and you should get an OK message.

### Configure the Override File

In order to make building as easy as possible, we have adopted the use of XCconfig files. Whilst this may seem unnecessary at first glance, it will make things much easier for future installs.

Right click the following link and copy it to your xdripswift folder:

[xDripConfigOverride.xcconfig](https://raw.githubusercontent.com/JohanDegraeve/xdripswift/0d485d1978bf90fb51b3a6cef8389f8daddb595d/xDripConfigOverride.xcconfig)

Open this file in TextEdit or Xcode and you will see the following structure. You will need to edit the lines highlighted in <span style="color:blue">blue</span>.

___
<span style="color:gray">MAIN_APP_DISPLAY_NAME = xDrip4iO5</span>

<span style="color:gray">// Put your team id here for signing<br /></span>
<span style="color:blue">// XDRIP_DEVELOPMENT_TEAM =</span>

<span style="color:gray">// Change to support running multiple apps simultaneously.<br /></span>
<span style="color:blue">// MAIN_APP_BUNDLE_IDENTIFIER = com.$(DEVELOPMENT_TEAM).xdripswift</span>
___

You should remove the "//" characters to uncomment these lines and in XDRIP_DEVELOPMENT_TEAM add your Development Team Identifier to this line.

If you **have** a paid Developer account, then you will probably already know this identifier. If not, then you can log into the Apple Developer Portal and look at the Membership section](https://developer.apple.com/account/#!/membership). You can find your ID here:

<img src="../install/img/developerid.png" />

Put this ID (your ID, not the example shown below) here:

<span style="color:red">//</span>XDRIP_DEVELOPMENT_TEAM = <span style="color:green">95C72J2362</span>

If you **don't** have a paid Developer account then you can always use something else. Examples:

<span style="color:red">//</span>XDRIP_DEVELOPMENT_TEAM = <span style="color:green">johnsmith</span>

<span style="color:red">//</span>XDRIP_DEVELOPMENT_TEAM = <span style="color:green">iloveinsulin</span>

Finally, just uncomment the MAIN_APP_BUNDLE_IDENTIFIER line. No need to edit anything else. Your file should now look like this:

___
<span style="color:gray">MAIN_APP_DISPLAY_NAME = xDrip4iO5</span>

<span style="color:gray">// Put your team id here for signing<br /></span>
<span style="color:green">XDRIP_DEVELOPMENT_TEAM = 95C77J2362</span><span style="color:blue"> *<--- here you put your unique ID*</span>

<span style="color:gray">// Change to support running multiple apps simultaneously.<br /></span>
<span style="color:green">MAIN_APP_BUNDLE_IDENTIFIER = com.$(DEVELOPMENT_TEAM).xdripswift</span>
___

### Build the Project

Now we're going to open the Workspace file. Go back to terminal and run the following command (again, inside your xdripswift folder).

    xed .

Open the xdrip file on the left of the screen and you should see that your Bundle Identifier has been correctly configured with the values you used in the previous step.

Now you'll need to "sign" the targets. Go to each one (xdrip + xDrip4iOS Widget Extension) and select your "Team" in the drop down Signing option.

Repeat this for each target, connect your iPhone to your Mac, select your device at the top of the screen (don't select a simulator!) and hit **Build** ("Play")
</br>
