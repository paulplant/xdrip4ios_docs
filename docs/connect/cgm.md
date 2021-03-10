# Connect to a CGM as a Master Device

In this page, we will go through the method of connecting a CGM system to xDrip4iOS so that this receives real-time CGM data from your sensor.

Firstly, make sure you have [correctly set](index.md) xDrip4iOS as a Master device and you have chosen the units that your BG should be displayed in.

Do not try and connect to your CGM transmitter from the Bluetooth menu on your iPhone. We will connect from within the xDrip4iOS app.

Before continuing, please check the [compatibility tables](../index.md#compatible-sensorstransmitters) to make sure that your CGM system is compatible.

## Freestyle Libre 

### Libre 2 with Direct Connection

This is only valid for the European Libre 2 sensor (aka Libre2 EU)

Firstly make sure that your Libre 2 sensor is started and working. If you scan the sensor with the LibreLink app, **can you see the values/graph**?

If **not**, start the sensor from the LibreLink app or put a new sensor on and start it. Then go back to the previous step until it works.

If **yes**, then let's continue. 

**Disable LibreLink Bluetooth Permission**

To avoid problems with the LibreLink app "stealing" the bluetooth connection from xDrip4iOS, we need to ensure that the LibreLink app has it's bluetooth permissions disabled.

Go to your iPhone Settings and scroll down to LibreLink. Select the app and in the options, disable Bluetooth.

**Connect to the Libre 2**

Go to the **Bluetooth** tab and chosee **CGM** as your **Device Type**, press **OK**.

If you already have a previous CGM added, you will get a warning to say that you can only have one CGM device added at a time. Please remove the previous device and try again.

In the Transmitter Types, select **Libre 2** and click OK.

You will get a message to Scan your sensor with the NFC antenna of your iPhone. You should scan the sensor as you would to start/read the sensor using the Libre app.

If you get an error message, please repeat adding the Libre 2 and scan again.

Once your sensor has been scanned successfully, you will see a message asking you to keep xDrip4iOS open whilst the bluetooth connection is made. Just leave your iPhone on the table and have a coffee. DO NOT play Roblox, watch Netflix or listen to Spotify. Put the phone down without touching it and walk away. Do it now.




