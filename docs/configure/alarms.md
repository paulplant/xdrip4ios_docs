# Setting Alarms

xDrip4iOS, the same as all other CGM apps, is able to alert you to certain events by sounding an alarm on your iPhone.

Alarms can be configured to happen for different reasons, such as:

- your blood glucose is getting too low
- your blood glucose is dropping very quickly
- your blood glucose is getting high
- you need to put in your initial calibration
- you have stopped getting readings from your sensor

We can also use alarms to function as **reminders** to remind us to:

- calibrate our sensor every *x* days
- stop and buy bread on the way home from work
- not really, but we're glad you're reading everything

There are **two steps** to configure an alarm in xDrip4iOS.

1. We define the **Alarm Types**. These are different types of alarms that we can use to alert us to different types of events.
<br /><br />
2. We define the **Alarms** themselves. These trigger different types of alarm based upon certain events that happen or conditions that we decide.


!!!info "Before we continue..."
    Let's just quickly get the concept clear. Take a deep breath and repeat after me...

       - An **Alarm Type** can be used for many different **Alarms**.<br /><br />
       - Any **Alarm** can only use one **Alarm Type** at a time.
___
## Alarm Types

Here we will define the different types of alarm that we will hear. 

If you go into Alarm Types, you will see that we there is a default Alarm Type set. We called it "Default"... because we're original and clever. You can modify this, or you can create your own Alarm Type.

If you want to add a new/custom Alarm Type, click the + button and configure it.

We can set the following parameters for an Alarm Type:

| Option &nbsp;&nbsp;&nbsp;| Description &nbsp;&nbsp;&nbsp; |
|:-------------- |:------------- |
| **Enabled**      | If enabled, any alarm assigned with this alarm type will alert us. If not enabled, the assigned alarm will not trigger  |
| **Name**      | Enter a name here such as "Loud", "Urgent" or "Quiet"  |
| **Vibrate**      | If enabled, the alarm will vibrate the phone  | 
| **Sound**      | Choose the sound that you want to play when the alarm is triggered  |
| **Override Mute**     | If enabled, the alarm will sound even if we have the phone in "Silent Mode"  |
| **Snooze Via Notification**      | If enabled, any notification will give us the option to "snooze" the alarm during *x* minutes  |
| **Default Snooze Time**      | Once we snooze an alarm, how many minutes should it wait before alarming again?  |

<br />

Once you've finished editing your Alarm Type, make sure you hit **Done** in the top-right corner. If you don't, you'll lose your changes.

___
## Alarms

Now that we have an Alarm Type configured, we can configure the individual Alarms.

An alarm will be triggered when the something meets a defined condition. For example you could define an alarm to be triggered:

- "Sound an **Low Alarm** whenever my blood glucose drops **below 60mg/dl**"

- "Sound a **High Alarm** if my blood glucose goes **over 250mg/dl**"

- "Sound a **Low Alarm** When my blood glucose drops **below 80mg/dl** during the night"

- "Sound an alarm if xDrip4iOS has been **Missing Readings** from my sensor in the last **30 minutes**"

- "Sound an alarm **72 hours** after I last calibrated my sensor to **remind me to calibrate** again"

In the above examples, you will see two things. The **Alarms** that are available and the **conditions** that we can set for them to be triggered.



___
## Volume Tests

They alarm will sound with the volume that your iPhone is set to.

This could mean that you have the volume turned right down and would then not hear anything.

In order to be able to quickly test what volume your alarms will sound at (before going to bed for example), you can click the Volume Test buttons. A sample Alarm sound will play and you can adjust the volume as required using the volume keys on the side of your iPhone. Then just click OK to stop the alarm.

If you have alarms that use the Override Mute function, then when silent mode is activated (the small switch above the volume keys), there will be a different volume level used. To test/set this level, click the Volume Test (Override Mute) button, set the level and click OK.