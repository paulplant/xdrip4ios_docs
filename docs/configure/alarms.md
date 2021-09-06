# Setting Alarms

<img src="../../img/Settings.png" style="zoom:75%;" />

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

<img src="../Alarm+Type.png" style="zoom:50%;" />

!!!info "Before we continue..."
    Let's just quickly get the concept clear. Take a deep breath and repeat after me...

       - An **Alarm Type** can be used for many different **Alarms**.<br /><br />
       - Any **Alarm** can only use one **Alarm Type** at a time.
</br>

___
## Alarm Types

Here we will define the different types of alarm that we will hear. 

<img src="../AlarmType.png" style="zoom:50%;" />

If you go into Alarm Types, you will see that we there is a default Alarm Type set. We called it "Default"... because we're original and clever. You can modify this, or you can create your own Alarm Type.

!!!info "Suggestion"
    You might find it easier to leave the default alarm disabled and create your own alarm type. Then you will use your custom alarm type only for the alarms you want to use. 

If you want to add a new/custom Alarm Type, click the + button top right and configure it.

We can set the following parameters for an Alarm Type:

<img src="../EditAlarmType.png" style="zoom:50%;" />

| Option &nbsp;&nbsp;&nbsp;| Description &nbsp;&nbsp;&nbsp; |
|:-------------- |:------------- |
| **Enabled**      | If enabled, any alarm assigned with this alarm type will alert us. If not enabled, the assigned alarm will not trigger  |
| **Name**      | Enter a name here such as "Loud", "Urgent" or "Quiet". The name can be anything you chose  |
| **Vibrate**      | If enabled, the alarm will vibrate the phone  |
| **Sound**      | Choose the sound that you want to play when the alarm is triggered  |
| **Override Mute**     | If enabled, the alarm will sound even if the phone is in "Silent Mode" (***except for Missed Readings***) |
| **Snooze Via Notification**      | If enabled, any notification will contain the option to "snooze" the alarm during *x* minutes  |
| **Default Snooze Time**      | Once an alarm is snoozed, how many minutes should it wait before alarming again?  |

<br />

Once you've finished editing your Alarm Type, make sure you hit **Done** in the top-right corner. If you don't, you'll lose your changes.

Eventually, you will have different alarm types, matching your needs in terms of sounds and vibrations.
Having several types will help you selectively disable some of them if necessary.

<img src="../AlarmTypes.png" style="zoom:50%;" />

</br>

___
## Alarms

Now that we have an Alarm Type configured, we can configure the individual Alarms.

<img src="../EditAlarm.png" style="zoom:50%;" />

An alarm will be triggered when the something meets a defined condition. For example you could define an alarm to be triggered:

- "Sound an **Low Alarm** whenever my blood glucose drops **below 60mg/dl**"

- "Sound a **High Alarm** if my blood glucose goes **over 250mg/dl**"

- "Sound a **Low Alarm** When my blood glucose drops **below 80mg/dl** during the night"

- "Sound an alarm if xDrip4iOS has been **Missing Readings** from my sensor in the last **30 minutes**"

- "Sound an alarm **72 hours** after I last calibrated my sensor to **remind me to calibrate** again"

In the above examples, you will see two things. The **Alarms** that are available and the **conditions** that we can set for them to be triggered.

Level alarms will trigger above (high) or below (low) a certain blood glucose level.

<img src="../LevelAlarm.png" style="zoom:50%;" />

Rise and drop alarms will trigger if blood glucose change over the last 2 readings (or 4 minutes for Libre 2 direct) is larger than the level you've setup.

<img src="../DeltaAlarm.png" style="zoom:50%;" />

Missed readings will trigger after the defined time without receiving any blood glucose data.

<img src="../MissReadAlarm.png" style="zoom:50%;" />

Calibrations needed alarm will trigger after the defined amount of hours since last calibration was entered in xDrip4iOS.

<img src="../CalibAlarm.png" style="zoom:50%;" />

Battery alarm will trigger when the battery falls below the defined percentage.

<img src="../BatteryAlarm.png" style="zoom:50%;" />

</br>

Each alarm will use one of the alarm types you created, select the one you'd like to be used for this alarm event:

<img src="../SelectAlarmType.png" style="zoom:50%;" />

</br>

You can also change the alarm type and threshold for certain moments of the day, for this you need to add alarms like in this example:

Say you'd like to have your Low Alarm to trigger only at night time (22:00 to 7:00). Select your low alarm and add an alarm with the + icon top right.

<img src="../AlarmTime1.png" style="zoom:50%;" />

On the new Low Alarm, change Apply from to 7:00 and Ok.

<img src="../AlarmTime2.png" style="zoom:50%;" />

Set the Alarm Type and Done.
You now have two different Low Alarms: Loud from 00:00 to 7:00 and quiet from 7:00 to 00:00.

<img src="../AlarmTime3.png" style="zoom:50%;" />

Now select the second alarm (starting at 7:00) and repeat the sequence with a new alarm starting at 22:00, alarm type Loud. Save.
You now have the Low Alarm trigger with the alarm type Loud from 22:00 to 7:00 and the rest of the day with Quiet.

<img src="../AlarmTime4.png" style="zoom:50%;" />

You could also have modified the threshold value for different moments of the day.

___
## Volume Tests

They alarm will sound with the volume that your iPhone is set to.

This could mean that you have the volume turned right down and would then not hear anything.

In order to be able to quickly test what volume your alarms will sound at (before going to bed for example), you can click the Volume Test buttons. A sample Alarm sound will play and you can adjust the volume as required using the volume keys on the side of your iPhone. Then just click OK to stop the alarm.

<img src="../TestOvrMuteOff.png" style="zoom:60%;" />

If you have alarms that use the Override Mute function, then when silent mode is activated (the small switch above the volume keys), there will be a different volume level used. To test/set this level, click the Volume Test (Override Mute) button, set the level and click OK.

<img src="../TestOvrMuteOn.png" style="zoom:60%;" />
