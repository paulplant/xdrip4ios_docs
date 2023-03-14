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
### Clone the xdripswift project

Let's start by grabbing a copy of the source code from Github and building the project.

You should open Terminal, navigate into your Documents folder (or wherever you prefer) and run the following command to clone the xDrip4iOS project:

    git clone --branch=master --recurse-submodules https://github.com/JohanDegraeve/xdripswift

This will create a new folder called xdripswift and it will copy all needed code into it. Once completed we should navigate into this folder:

    cd xdripswift

### Configure the Override File

In order to make building as easy as possible, we have adopted the use of XCconfig files. Whilst this may seem unnecessary at first glance, it will make things much easier for future installs.

Right click the following link, chose the "**Save Link As...**" or "**Download Linked File As...**" option and save the file to your xdripswift folder:

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

<img src="../img/developerid.png" />

Put this ID (your ID, not the example shown below) here:

XDRIP_DEVELOPMENT_TEAM = <span style="color:green">95C72J2362</span>

Finally, just uncomment the MAIN_APP_BUNDLE_IDENTIFIER line. No need to edit anything else. Your file should now look like this:

___
<span style="color:gray">MAIN_APP_DISPLAY_NAME = xDrip4iO5</span>

<span style="color:gray">// Put your team id here for signing<br /></span>
<span style="color:green">XDRIP_DEVELOPMENT_TEAM = 95C77J2362</span><span style="color:blue"> *<--- here you put your unique ID*</span>

<span style="color:gray">// Change to support running multiple apps simultaneously.<br /></span>
<span style="color:green">MAIN_APP_BUNDLE_IDENTIFIER = com.$(DEVELOPMENT_TEAM).xdripswift</span>

Make sure you save/close the file and exit out of the editor/Xcode before continuing.

___
### Build the Project

Now we're going to open the Workspace file. Go back to terminal and run the following command (again, inside your xdripswift folder).

    xed .

(If you prefer to do this manually you can open the xdrip.xcworkspace file from within Finder. Do *not* try opening the xdrip.xcodeproj file as it *will not work* for building the app)

Open the xdrip file on the left of the screen and you should see that your Bundle Identifier has been correctly configured with the values you used in the previous step.

Now you'll need to "sign" the targets in order to allow Xcode to create a provisioning profile to be able to install the app to your iPhone. Go to the **Signing & Capabilities** tab one and select your **Team** in the drop down Signing option for each target.

Please note that there are **four** targets to sign:

1. xdrip
2. xDrip4iOS Widget
3. Watch App
4. Watch App Watchkit Extension

Repeat this for each target, connect your iPhone to your Mac, select your device at the top of the screen (don't select a simulator!) and hit **Build** ("Play")
</br>

___

### How do I Update?

From time to time, we will release updates to the xDrip4iOS application. When this happens, we will always merge the updated code into the master branch in Github and with this code, we will update the original Testflight release.

We would always recommend keeping your build up-to-date with the latest release. Apart from new features, we will often include fixes and improvements in every release.

You have two options for updating your build:

1. Delete everything and start again. We don't recommend this, but it would work. Just delete the xdripswift folder and follow all instructions again from the top of this page.</br></br>
2. Use **git** to **pull** in the latest code changes (commits) and hit re-build. This is the preffered method and is what we will discuss below

Why do we recommend option (2)? It is simple. If you make a mistake in downloading and configuring the freshly cloned code in (1), then your app will install as a completely new app. What you want to do is to overwrite the original app and keep all settings/data. This is why we prefer option (2).

So we are starting with your existing xdripswift folder. This has the code you previously cloned and where you had edited xDripConfigOverride and also you had installed the cocoapods dependencies and signed the targets.

First we are going to save a copy of these local changes that you have made.

Make sure that you have closed Xcode completely, open **Terminal** and go to the **xdripswift** folder and run:

    git stash

This will remove your changes and store them to one side whilst we do other things. We need to do this to remove your modifications before merging in the latest changes from the master branch in the main repository.

Now we have returned your local copy to be the same as when it was first cloned, we need to pull downstream the changes in master and merge them into your local copy:

    git pull --force

This is a single command to perform a git "fetch" followed by a git "merge" to pull all latest changes and merge them into your local copy.

Now we need to re-apply the previously saved (stashed) changes. We do this by running:

    git stash pop

We should now have the code fully updated and your local changes (signing etc) applied to the "new" code.

Now we're going to open the Workspace file as before. Go back to Terminal and run the following command (again, inside your xdripswift folder).

    xed .

Now continue with the steps as before in order to build xDrip4iOS.

___
## Update Problems?

Xcode can sometimes make this tricky when it comes to simply describing a series of timestamped text edits to code files (which is the basic idea behind source-code control - in this case we use Github). 

The main **xdrip.xcodeproj** and **project.pbxproj** files can easily get out of sync when big changes are made to the project structure and build settings and this makes it difficult to re-apply your previous changes. The update to 4.8.0 included very big changes with the addition of the Apple Watch app and new build variables/settings aimed to make things easier for newer builders.

When this happens, it is possible that you will get a merge error in Terminal. If this happens, you must fix it before trying to open the Workspace file and build.

    CONFLICT (content): Merge conflict in xdrip.xcodeproj/project.pbxproj

If you see the above error, the easiest way is to simply start all over again. If you already built once, then it will take you just a few minutes.

Please follow these steps:

1. Using Finder, browse to your xdripswift folder and **copy your modified xDripConfigOverride file to the Desktop** or wherever you want.
2. **Delete** your xdripswift folder completely.
3. Go back to the Build instructions and start the whole process again to **clone** a new/updated copy of the master branch. 
4. Run "**install pod**" again from Terminal inside your new xdripswift folder.
5. This time, copy in your previously modified xDripConfigOverride file before simply opening the workspace with "**xed .**" as before.

Assuming that you really did follow the build instructions correctly the first time and didn't edit anything else, then you should be able to immediately just build the new version with no problems.