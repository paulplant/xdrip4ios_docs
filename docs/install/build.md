# How to Build xDrip4iOS using Xcode

Project repository [here](https://github.com/JohanDegraeve/xdripswift)

___
### Install the Cocoa Pods Framework to your Mac

If this is the first time that you have built xDrip4iOS on your Mac, then you will need to install a set of frameworks called CocoaPods. If you have previously installed CocoaPods, you can skip this step.

Enter the following command into Terminal:

    sudo gem install cocoapods

This should install the dependencies and give you an OK message.

### Clone the xdripswift project

You should go into your Documents folder (or wherever you prefer) and run the following command to clone the xDrip4iOS project:

    git clone --branch=master --recurse-submodules https://github.com/JohanDegraeve/xdripswift

This will create a new folder called xdripswift. Once completed we should navigate into this folder:

    cd xdripswift

### Install Cocoa Pods Dependencies

Earlier we installed the full Cocoa Pods framework onto your system. Now we will go into the cloned project folder and install the individual project dependencies there:

    pod install

Again, you will see some activity and you should get an OK message.

Open the WorkSpace file by typing:

   xed .

### Set the Bundle Identifier

Here you should create a unique Bundle Identifier for each target. The default value in the project is:

net.johandegraeve.xdripswift<br />
net.johandegraeve.xdripswift.xDrip4iOS-Widget

Obviously, this is already in use by Johan so we need to change them.

You should change the part that says "**net.johndegraeve**" to something that nobody else is using. You can use anything you want such as:

- **com.ilovetheweekend**.xdripswift
- **com.ilovetheweekend**.xdripswift.xDrip4iOS-Widget
<br /><br />

- **net.keithrichards**.xdripswift
- **net.keithrichards**.xdripswift.xDrip4iOS-Widget
<br /><br />

- **com.anything-i-want**.xdripswift
- **com.anything-i-want**.xdripswift.xDrip4iOS-Widget

Just invent something and try it. If somebody else is already using this identifier, then you'll get an error and can just chose another one.

Now you should sign both targets with your Development Team, connect your iPhone to your Mac, select your device and hit **Build** ("Play")


</br>