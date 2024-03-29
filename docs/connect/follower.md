# Connect to Nightscout as a Follower

<img src="../../img/Settings.png" style="zoom:75%;" />

In this page, we will go through the method of connecting xDrip4iOS to an existing Nightscout instance.

This will allow you to "follow" another person (child, loved one or patient) and see their CGM value and graph in real-time.

Firstly, make sure you have valid CGM data being sent into the Nightscout site by a working master device/system.


!!!info "Follower Restrictions"
    Please note that when used in Follower Mode, xDrip4iOS cannot connect to any CGM system/sensor. For this reason you will see that the Calibration and Sensor buttons are disabled.

In **Settings**, check that you are set to **Follower** mode. If not, click the option once to change modes.

<img src="../Follower.png" style="zoom:50%;" />

___

In order to connect xDrip4iOS to Nightscout as a Follower, in the Settings Menu, select **Enable Nightscout**.

<img src="../Nightscout.png" style="zoom:50%;" />

You should enter your Nightscout **URL** as per the service you want to follow (if you don't know this, the master user will usually be able to give you this information).

URL examples (change *mynightscout* and *12345* as necessary):

- **Heroku/Mongo**: ```https://mynightscout.herokuapp.com```
- **ns.10be.de** *(1)*: ```https://mynightscout.10be.de```  Port: ```12345```
- **T1Pal**: ```https://mynightscout.t1pal.com``` (*Note: you'll find your public Url in [the Social page](https://t1pal.com/account/sites/my#Views)*)

*(1) *If your URL needs a port number to access the service (such as the default mode of ns.10be.de), then enter this number in **Port**.