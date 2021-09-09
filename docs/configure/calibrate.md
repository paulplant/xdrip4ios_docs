# Calibration of xDrip4iOS

DISCLAIMER: No matter which calibration method you decide to use and/or how good you are in calibrating the BG readings, there are many reasons and factors why Xdrip4iOS can show values that differ greatly from your actual blood glucose. Due to this, use careful consideration if you are about to apply a correction bolus because the app says that you have a high blood glucose OR before you decide to take in some fast carbs, because the app is saying you have a hypo, but you don't feel like it at all. 

It's always recommended to take a proper finger prick test, if you have any doubts about the accurace of the reading in the app.

## What does "Calibration" mean?

Calibration means Xdrip4iOS functionality with which user can make the blood glucose (BG) readings provided by the sensor to become more accurate before they are shown in the app.

___

## Why to Calibrate?

BG readings provided by your sensor are so called "raw" values and the accuracy of these raw values depend on many things. Typical variable is the time of how long the sensor has been attached to your skin; sensors are typically less accurate "right out of the box" and also 1-3 days before they expire. This is natural behaviour of sensors. Also even sensors themselves do vary: sometimes you get an accurate one which behaves nicely the whole usage period and throughout the BG range, when the other time the sensor is all the time all over the place and might even stop working before the official usage period end.

If you find that you are not happy with the (non-calibrated) accuracy of your current sensor, the calibration methods provided by Xdrip4iOS help you to mitigate the above mentioned variables to make the BG readings to be more accurate.

___

## What are the different ways to calibrate BG readings in Xdrip4iOS?

Xdrip4iOS application offers three different ways how the app interprets the raw BG values provided by the sensor. Each Xdrip4iOS user needs to consider that what is the best method for him/her to use.

1. Use Libre algorhythm
2. Single-point calibration
3. Multi-point calibration

### Libre algorhythm

WHEN TO USE THIS: Choose this method, if you have just started to use Xdrip4iOS and/or you are not (yet) familiar enough with the concept of calibration that you would like to try it out and/or you just want a simple setup and you are ok with the inaccuracies that come from this method. 

Libre algorhythm is not an actual calibration method at all, but more of a basic setting in the app for those users, who don't want to spend time on thinking when or how to calibrate. For this method the app has a specific built-in algorhythm that applies a correction to the BG reading provided by the sensor and then the corrected BG reading is shown to the user. The user is not able to impact to the correction which is done by the algorhythm.

NOTE: Even if Xdrip4iOS says that it uses *Libre* algorhythm, there most likely are differences between the readings shown by LibreLink app and readings shown by Xdrip4iOS.

NOTE #2: Please expect that there can be even relatively large differences between Xdrip4iOS and your actual blood glucose reading.

### Single-point calibration

WHEN TO USE THIS: Choose this method, when you want to get more accurate BG readings from the app and you are ready to apply a calibration, but you don't necessarily want to calibrate that often.

Single-point calibration means a way of calibration, where you make only one calibration based on which the app then applies a correction for the raw values that the sensor is sending. Single-point calibration applies correction only via intercept of the calibration curve (please read below "What does Calibration do?").

### Multi-point calibration

WHEN TO USE THIS: If you want the most accurate BG readings from the app and you are ready to pay more attention and to use more time on calibration.

Multi-point calibration means a way of calibration, where user can calibrate in different areas of the BG range. This means that the calibration curve can take into account the differences in the sensor raw value accuracy at low-end of BG range and in the high-end of BG range. The first calibration adjusts only the intercept of the calibration curve (please read below "What does Calibration do?") but the following calibrations after this adjust both the slope and the intercept. 

In *theory* the more calibrations are added the more accurate the calibration becomes. However, in practice even just two good calibrations (one on the low-end of BG range and the other on the high-end) make the calibration very accurate.

___


## What does Calibration do?

As described above, calibration is a way to reduce the inaccuracies that are coming from the sensor that you use. In practise the calibration is stored as a calibration curve in the app. This curve is used to apply a correction to the value provided by the sensor. This graph is not visible in the app, but can be described as a combination of slope and intercept.:

### Slope
Slope describes the steepness of the calibration curve. Slope (in this context of calibration!) can be only positive and is typically something between 0.7-1.3. Slope is a multiplier that is applied to the raw value of the sensor throughout the BG range.

### Intercept
Intercept describes a fixed correction that is added (when positive) or deducted (when negative) from the raw value. Intercept can be also 0.

EXAMPLE #1:
Slope: 1.0
Intercept: 0.0

= No calibration. Raw value is shown as-is in the app: if sensor gives 5.0 mmol reading, the app shows 5.0 mmol reading.

EXAMPLE #2:
Slope: 1.0
Intercept: 0.3

= Typical example of single-point calibration, where the calibration applies a small, fixed correction over the whole BG range. Remember that intercept can also be negative. In practice 0,3 mmol is added (deducted, if negative intercept) to any sensor raw value: if sensor gives a raw value of 5.0 mmol, the app shows 5.3 mmol, if the sensor gives a raw value of 9.3 mmol, the app shows 9.6 mmol.

EXAMPLE #3:
Slope: 1.2
Intercept: 0.0

= Example of a calibration, where only the slope of the calibration is adjusted. In practice this type of a calibration means that throughout the BG range, a multiplier of 1.2 is applied to the raw value: if sensor gives a raw value of 5.0 mmol, the app shows 6.0 mmol (5.0 x 1.2), if the sensor gives a raw value of 9.3 mmol, the app shows 11.2 mmol (9.3 x 1.2).

EXAMPLE #4:
Slope: 1.2
Intercept: 0.3

= Typical example of multi-point calibration after the 2nd (or further) calibration value has been applied. This applies both add/deduct as per the intercept and also a multiplier as per the slope: if sensor gives a raw value of 5.0 mmol, the app shows 6.3 mmol (5.0 x 1.2 + 0.3), if the sensor gives a raw value of 9.3 mmol, the app shows 11.5 mmol (9.3 x 1.2 + 0.3).

___


## Calibration Best Practices

* While a finger prick gives you an accurate BG reading straight from your blood at that time, a sensor attached to your skin measures and estimates BG readings from interstitial fluid in your skin. When your actual BG fluctuates, these changes appear in interstitial fluid only after a delay. This delay can be anything between 5-20 mins. This means that your BG must have been steady when you take a finger prick and must continue remaining steady in the app after you have applied a calibration. Calibration makes the BG reading typically to jump up or down, but the line should remain horizontal after this. 
   * You need to understand that the finger prick reading you see in BG reader, is shown in Xdrip4iOS only after the above mentioned delay. If you calibrate when your BG is steady, you know that you are giving the app a chance to calculate the best possible calibration correction. If you calibrate, when BG is not steady, you are shooting a moving target.
   * Being steady does not mean only that your actual BG is steady but that also the reading in the app is steady. Probably everyone who wears a sensor and has gone to swimming, in sauna, out in the cold, layed on a sofa pressure on sensor etc. etc. have seen that the sensor reading might suddenly rise or fall. If you calibrate when this happens, you can be certain that the applied calibration is bad and you get very inaccurate BG readings from the app.
   * Over time, you might learn to make calibrations also when your BG is not 100 % steady, e.g. *slowly* coming down. This is however not recommended for newbies due to a high probability of making an error.
* Calibrate only when you are in range. There are two reasons to this: 
   * 1) you should not be too interested if you are 14 or 16 mmol or if you are 2.9 or 3.1 mmol. Either or, you know that you have a hyper or a hypo and you need to take actions. At this time the BG reading in the app and its accuracy does not matter *that* much. Hence, if you can get the in-range accuracy to be good, 
   * 2)Sensors themselves are the most accurate in range area and inaccuracies increase when outside. As we know, we want as accurate readings as possible, when calibrating, so you don't want to apply calibrations on top of inaccurate sensor readings.
   * Of course, if the app says 3.0 mmol but your actual BG (as per a finger prick) says 4.0 (and your BG is steady!), you can calibrate. No T1D wants to hear low alarms blazing, when they are not actually hypo'ing.
* When taking a finger prick:
   * Use as accurate BG reader as possible
   * Wash your hands before you take the reading
   * Don't squeeze your fingertip to get a blood drop out
* You might screw an earlier nice calibration with just only one bad new calibration value
* When it comes to calibration, less is often more. You are not supposed to calibrate each and every day. If you feel like it and your BG is steady, you can do it, but it's completely fine 
* It's more critical to be accurate in the lower-end of the scale than on the high side. So prioritize the accuracy of the low-end calibrations. A good practice is to change from old sensor to a new one, when your BG is at the low-end and steady. That way you can apply right away a good low-end calibration and be certain that at least the low alarms go off at the right time.
* If you calibrate during the 1st day of a sensor, that same calibration is most likely not accurate on the 10th day. It's good practice to calibrate again, when you see from the app that your BG is steady.

___

## How to calibrate in Xdrip4iOS?

Alright, if you've read these instructions this far, you are ready for calibration. This section gives you instructions on how you will apply a new calibration in Xdrip4iOS.

1. Select the calibration method you want to use: either "Single-point calibration" or "Multi-point calibration".
2. On the main screen of the app, click "Calibrate"
   * If you have just connected a new sensor, the app does not allow you to calibrate right away. You need to wait until the app gets at least two BG readings from the sensor, before a calibration can be applied
3. A pop-up opens, which asks you to enter a calibration value.

DONE! After this, the app starts to apply a correction to all the BG readings coming from the sensor. If you have a Nightscout installation

NOTE: If you notice that the calibration that you applied was bad (for whatever reason) and made the BG readings very inaccurate, you can reset all the calibrations by stopping and starting the sensor. Unfortunately it is not possible to remove individual calibration values

NOTE #2: If you change the calibration method, it resets all the previous calibrations.

___


## Other notes

* By default, Xdrip4iOS has alerts to remind you to perform a calibration. If the app alerts you about this, it doesn't mean that you _must_ do a new calibration. If you feel that these alerts/reminders occur too often, you can increase their interval. Often people turn calibration alerts even completely off.
* If you have a Nightscout installation, it is possible to see calibration curve there in the reports. 
    * Sometimes a new calibration value makes the calibration slope and/or intercept to become something crazy. If this happens, you will see it in this report.
    * It is to be noted that in Nightscout reports, the calibration report shows the graph as inverted: sensor raw value on Y axis and BG reading value after the calibration on the X axis. This means that you need to know how to read the graph and slope and intercept values reported by Nightscout - this part is not explained in these instructions.

___

 

</br>
