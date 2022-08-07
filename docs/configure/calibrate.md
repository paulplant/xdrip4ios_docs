# Calibration of xDrip4iOS

!!!warning "Disclaimer"
    No matter which calibration method you decide to use and/or how good you are in calibrating, there are many reasons and factors why xDrip4iOS can show values that differ greatly from your actual blood glucose. Due to this, use careful consideration if you are about to apply a correction bolus because the app says that you have a high blood glucose OR before you decide to take in some fast carbs, because the app is saying you have a hypo, but you don't feel like it at all. 
    

    It is always recommended to take a proper finger prick test if you have any doubts about the accuracy of the reading shown in the app.

!!!info "Please note"
    The most of the example blood glucose values in this instruction text is in unit of mmol/l. You can transform these values to mg/dl by multiplying the mmol/l figure by 18 (i.e. 1 mmol/l = 18 mg/dl).

___

## What does "Calibration" mean?

Calibration is a functionality in many CGM apps with which user can make the calculations that use the sensor glucose (SG) readings sent by the sensor become much more accurate and closer to real blood glucose (BG).

___

## Why do we need to calibrate?

SG readings sent by your sensor are so called "raw" values and the accuracy of these raw values depend on many things. Typical variables that have an impact are the time of how long the sensor has been attached to your skin; sensors are typically less accurate "right out of the box" and also 1-3 days before they expire. This is a natural behaviour of sensors and is completely normal. You might have also inserted the sensor into an area on your skin where it's harder for the sensor to get accurate readings. Also even sensors themselves vary; sometimes you get an accurate one which behaves nicely the whole time it is inserted and throughout the BG range, the other time the sensor can be all over the place and might even stop working before the official usage period ends.

All this means that if you find that you are not happy with the (non-calibrated) accuracy of your current sensor, the calibration methods provided by xDrip4iOS help you to mitigate the above mentioned variables to make the BG readings in the app much more accurate.

!!!warning "Important"
    **No calibration can accurate readings provided by a faulty/noisy sensor.** If the sensor is providing erratic and highly fluctuating SG values, it is impossible for any application to correct these and show accurate readings to the user. For this reason it might be difficult to calibrate, when a sensor is new and the readings have not yet steadied out.

___

## Algorithms and calibration methods

xDrip4iOS application offers three different ways how the app interprets the raw SG values provided by the sensor. Each xDrip4iOS user needs to consider that what is the best method for *themselves* to use.

1. Libre algorithm *(basic)*
2. xDrip algorithm with single-point calibration *(recommended)*
3. xDrip algorithm with multi-point calibration *(advanced use)*

### Libre algorithm

Choose this method if you have just started to use xDrip4iOS and/or you are not (yet) familiar enough with the concept of calibration that you would like to try it out and/or you just want a simple setup and you are ok with the inaccuracies that come from this method. 

Libre algorithm is not an actual calibration method at all, but more of a default setting in the app for those users, who don't want to spend time on thinking when or how to calibrate. For this method the app has a specific built-in algorithm that applies a correction to the BG reading provided by the sensor and then the corrected BG reading is shown to the user. The user is not able to impact to the correction which is done by the algorithm.

!!!info "Please note when using Libre algorithm!"
    * Even if xDrip4iOS says that it uses the *Libre* algorithm, there will most likely be small differences between the readings shown by the LibreLink app and readings shown by xDrip4iOS.
    
    * Please expect that due to the lack of calibration there could be relatively large differences between the reading shown in xDrip4iOS and your actual blood glucose reading.

### xDrip algorithm with single-point calibration

Choose this method, when you want to get more accurate readings from the app and you are ready to apply a calibration, but you don't necessarily want to calibrate that often.

Single-point calibration is a way of calibration where you make only one calibration based on which the app then applies a fixed positive or negative correction for the raw values that the sensor is sending. Single-point calibration applies correction only via intercept of the calibration curve (please read below "Advanced Calibration Explanations").

### xDrip algorithm with multi-point calibration

If you want the most accurate readings from the app and you are ready to pay more attention and to use more time on calibration.

Multi-point calibration allows a way of calibration in which the user can enter different calibration values in different areas of the BG range which are then all taken into account when the app calculates the calibration curve. This means that the calibration curve can take into account the differences in the sensor raw value accuracy at low-end of BG range and in the high-end of BG range. The first calibration adjusts only the intercept of the calibration curve (please read below "Advanced Calibration Explanations") but the following calibrations after this adjust both the slope and the intercept. If done correctly, this calibration method can provide very accurate readings in the app, but if done wrongly also the magnitude of error can be much larger.

In *theory* the more calibrations are added the more accurate the calibration becomes. However, in practice even just two good calibrations (one on the low-end of BG range and the other on the high-end) can make the calibration very accurate. This means that e.g. regular twice-a-day calibrations are not needed and they actually increase the possibility that the user eventually applies a faulty calibration, which makes the whole calibration go bad.

___

## Advanced Calibration Explanations

As described above, calibration is a way to reduce the inaccuracies that are coming from the sensor that you use. This section explains in more detail how Xdrip4iOS transforms the raw SG readings into calibrated BG readings that are then shown to the user in the main screen of the app.

In practise the calibration is stored as a calibration curve in the app. This curve is used to apply a correction to the value provided by the sensor. This graph is not visible in the app, but can be described as a combination of slope and intercept - it makes it easier to understand these concepts, if you remember the lessons about 1st degree equations from the time you were in school :)

### Slope
The **Slope** describes the steepness/angle of the calibration curve. Slope (in the context of calibration) can be only positive and is typically something between 0,7-1,3. Slope is a multiplier that is applied to the raw value of the sensor throughout the BG range. If there is no calibration, slope gets a value of 1,0.

### Intercept
The **Intercept** describes a fixed correction that is added (when positive) or deducted (when negative) from the raw value. Typical values for intercept are between -2,0.... +2,0 (in mmol/l). If there is no calibration, intercept gets a value of 0.



!!!info "Example #1"
    **Slope** = 1,0 / **Intercept** = 0,0
    
    **Result** = No calibration. Raw value from sensor is shown as-is in the app: if sensor gives 5,0 mmol/l reading, the app shows 5,0 mmol/l reading.

!!!info "Example #2"
    **Slope** = 1,0 / **Intercept** = 0,3
    
    Typical example of single-point calibration, where the calibration applies a small, fixed correction over the whole BG range. Remember that intercept can also be negative. In practice 0,3 mmol/l is added (deducted, if negative intercept) to any sensor raw value: if sensor gives a raw value of 5,0 mmol/l, the app shows 5,3 mmol/l, if the sensor gives a raw value of 9,3 mmol/l, the app shows 9,6 mmol/l.


!!!info "Example #13"
    **Slope** = 1,2 / **Intercept** = 0,0
    
    Example of a calibration, where only the slope of the calibration is adjusted. In practice this type of a calibration means that throughout the BG range, a multiplier of 1,2 is applied to the raw value: if sensor gives a raw value of 5,0 mmol/l, the app shows 6.0 mmol/l (5,0 x 1,2), if the sensor gives a raw value of 9,3 mmol/l, the app shows 11,2 mmol/l (9,3 x 1,2).


!!!info "Example #4"
    **Slope** = 1,2 / **Intercept** = 0,3
    
    Typical example of multi-point calibration after the 2nd (or further) calibration has been done. This applies both the fixed correction as per the intercept and also a multiplier as per the slope value: if sensor gives a raw value of 5,0 mmol/l, the app shows 6,3 mmol/l (5,0 x 1,2 + 0,3), if the sensor gives a raw value of 9,3 mmol/l, the app shows 11,5 mmol/l (9,3 x 1,2 + 0,3).
___


## Calibration Best Practices

* **Calibrate only when your BG is steady.** While a finger prick gives you an accurate BG reading straight from your blood at that time, a sensor attached to your skin measures and estimates BG readings from interstitial fluid under your skin. When your actual BG fluctuates, these changes appear in interstitial fluid only after a delay. This delay can be anything between 5-20 mins. This means that your BG must have been steady when you take a finger prick and must continue remaining steady in the app after you have applied a calibration. Calibration makes the BG reading typically to jump up or down, but the line should remain horizontal after this. <br />
  
     * You need to understand that the finger prick reading you see in BG reader, is shown in xDrip4iOS only after the above mentioned delay. If you calibrate when your BG is steady, you know that you are giving the app a chance to calculate the best possible calibration correction. If you calibrate, when BG is not steady, you are shooting a moving target.
     * Being steady does not mean only that your actual BG is steady but that also the reading in the app is steady. Probably everyone who wears a sensor and has gone to swimming, in sauna, out in the cold, layed on a sofa pressure on sensor etc. etc. have seen that the sensor reading might suddenly rise or fall. If you calibrate when this happens, you can be certain that the applied calibration is bad and you get very inaccurate BG readings from the app.
     * Over time, you might learn to make calibrations also when your BG is not 100 % steady, e.g. *slowly* coming down. This is however not recommended for newbies due to a high probability of making an error.
  <br /><br />

* **Calibrate only when you are in range.** There are two reasons to this: <br />
  
     * First reason is that you should not be too interested if you are 14 or 16 mmol/l or if you are 2,9 or 3,1 mmol/l. Either or, you know that you have a hyper or a hypo and you need to take actions. At this time the BG reading in the app and its accuracy does not matter *that* much. I.e. aim to get the in-range accuracy to be good and settle for that out-of-range accuracy might be so-so.
     * Second reason is that the sensors themselves are the most accurate in range area and their inaccuracies increase when BG is outside the normal range. As we know, we want as accurate readings as possible, when calibrating, so you don't want to apply calibrations on top of inaccurate sensor readings.
     * Of course, if the app says that you are out of range and shows 3,0 mmol/l but your actual BG (as per a finger prick) says 4,0 (*and* your BG is steady), you can calibrate. No T1D wants to hear low alarms blazing, when they are not actually hypo'ing.
  <br /><br />
  
* **Ensure you minimize the margin of error, when taking a finger prick**:<br />
  
     * Use as accurate BG reader as possible. If you know that your sensor is inaccurate, consider updating it to a good one.
     * Use strips that have not expired. While it's *possible* to use expired strips and get accurate readings with them as well, do you want to take the chance?
     * Wash your hands before you take the reading. You might have some residues in your fingers, which impact the measurement - wash them off first.
     * Don't squeeze your fingertip to get a blood drop out.
  <br /><br />

* Everyone knows how wild the sensor readings might be during the first 12-24 hours after a new sensor has been installed. This happens because the area where you applied the sensor is not yet used to the small filament that is inside your skin and via which the sensor takes readings. These sudden changes make also calibration more difficult. You can mitigate these if you **attach a new sensor on your skin 12-24 hours *before* you actually take it in use**. That way your skin has time to get used to the sensor and the readings are much more calm, when you start the sensor.
<br /><br />

* If you calibrate during the 1st day of a sensor, that same calibration is most likely not accurate on the 10th day. **It's good practice every once in a while to make a BG check with a finger prick when your BG is stable**, and f the reading in Xdrip4iOS differs from that, you can consider calibrating. However, it doesn't necessarily make sense to calibrate if the difference is something like 0,1-0,4 mmol/l, because even the most accurate BG readers have some fault tolerance.
<br /><br />

* It's more critical to be accurate in the lower-end of the scale than on the high side. So **prioritize the accuracy of the low-end calibrations**. For this it helps if you have installed (but not yet taken in to use) a new sensor but still taking the SG readings to Xdrip4iOS from the old one; when the readings are stable and at the low-end of the BG range, make a switch from old sensor to the new one. This way you can apply right away a good low-end calibration and be certain that at least the low alarms go off at the right time. 
<br /><br />

* You might screw an earlier nice calibration with just only one bad new calibration value. So **don't calibrate for the sake of the calibration itself**. When it comes to calibration, less is often more. You are *not* supposed to calibrate each and every day. If you feel like it and your BG is steady, you can do it, but it's completely fine to calibrate even just 3-4 times during the lifespan of a sensor. Make rather one good and accurate calibration than five sketchy ones. 

___

## How to calibrate in xDrip4iOS?

<img src="../img/CalibrateIcon.png" style="zoom:50%;" />

Alright, if you've read these instructions this far, you are ready for calibration. This section gives you instructions on how you will apply a new calibration in xDrip4iOS.

1. Select the calibration method you want to use: either "Single-point calibration" or "Multi-point calibration". You can make this selection in "Bluetooth" tab in the app inside your transmitter.
2. On the main screen of the app, select "Calibrate"
   * If you have just connected a new sensor (or resetted the calibrations by stop->start sensor), the app does not allow you to calibrate right away. You need to wait until the app gets at least two BG readings from the sensor, before a calibration can be applied.
3. A pop-up opens, which asks you to enter a calibration value. Here you enter the value from your BG reader after a finger prick.

**DONE!** 

After this, the app calculates the calibration curve as per the provided calibration value and starts to apply a correction to all the further BG readings coming from the sensor. Depending on the size of the calibration you did, you may notice right away that the graph on the screen of Xdrip4iOS jumped up or down - this is completely normal. It is also normal that the next BG value is not exactly the same value that you just entered as a calibration value. This happens because the entered calibration value is first used to calculate the new calibration curve and only this calibration curve (see "Advanced Calibration Explanations") is used to calculate the shown BG values in the app.

Remember to monitor the readings in the app after a calibration; if they start to go up or down within 15-20 mins, there is a chance that your BG was not actually steady at the moment of the calibration, i.e. your actual BG had already started to change, but because this change was not yet visible in the app, the calibration was not accurate. Practice makes perfect and over time you might learn to do a relatively accurate calibrations, even when your BG is going *slowly* up or down, but the ground rule is: BG steady and in range. 


!!!info "Please note"
    * If you notice that the calibration that you applied was bad (for whatever reason) and made the BG readings inaccurate, you can reset all the calibrations by stopping and starting the sensor. Unfortunately it is not possible to remove individual calibration values<br /><br />
    * If you change the calibration method, it resets all the previous calibrations.

___


## Other notes

* By default, xDrip4iOS has alerts to remind you to perform a calibration. If the app alerts you about this, it doesn't mean that you _must_ do a new calibration. If you feel that these alerts/reminders occur too often, you can increase their interval. Often people turn calibration alerts even completely off.<br /><br />
* Sometimes a new calibration value makes the calibration slope and/or intercept to become something crazy without user noticing it right away. If you have a Nightscout installation, it is possible to see calibration curve there in the reports. There is a specific "Calibrations" report type for this.<br /><br />
    * This report returns you the current and the past calibration graphs so that you can look at them and assess their accuracy. You can also compare the previous curve and the current curve and think how the calibration that you just did changed the curve.<br /><br />
    * It is to be noted that in Nightscout reports, the calibration report shows the graph as inverted: sensor raw value is on Y axis and BG reading value after the calibration on the X axis. This means that you need to know how to read the graph and slope and intercept values reported by Nightscout - this part is not explained in these instructions more than these below:<br /><br />
        * Values in these reports are shown based on 'mg/dl' and multiplied by 1000. <br /><br />
        * On the report, the intercept value of "-24000" is actually a positive intercept of 24 mg/dl or 1,5 mmol/l <br /><br />
        * On the report, the slope value of 1100 is actually slope of 0,91  (1/1,1)

