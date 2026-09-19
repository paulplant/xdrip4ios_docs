# How to ask for help

Use this guide to explain your setup and the problem when asking for help.

We are happy to help. You do not need to be a technical expert, and you do not need to know what caused the problem.

xDrip4iOS is a community project. The people helping are volunteers giving their own time. They cannot see your phone or know how you have set up the app unless you explain it.

“It doesn't work” tells us that something is wrong, but not enough to work out why. Without some basic details, we may only be able to ask more questions. A few clear sentences at the start help everyone get to a useful answer sooner.

## Start with your CGM or system

**Always tell us which CGM or system you are using first.** Give the exact model, such as Dexcom G6, Dexcom G7, Libre 2, or Libre 2 Plus. “Dexcom” or “Libre” alone is not enough to identify your setup.

Then explain how you get readings into xDrip4iOS. Does it connect directly to the sensor, use a transmitter such as MiaoMiao or Bubble, or follow readings through a service such as LibreLinkUp, Dexcom Share, Nightscout, or CareLink?

Include other apps, receivers, or pumps involved, such as CamAPS. If you follow someone else's readings, describe their CGM setup as well as the phone where the problem appears. If you are unsure, say what you know rather than guessing.

You can check the selected source in **Settings > Data Source**. You do not need to understand terms such as Master or Follower to ask for help. A description in your own words is fine.

## Explain what is happening

### What are you trying to do?

Tell us what you expect to happen. For example, are you connecting a sensor for the first time, following someone else's readings, showing glucose on a watch, or trying to receive an alarm?

### What happens instead?

Describe what you actually see. Is the reading old? Does the device stay on “Scanning”? Does an error appear? Does the app unexpectedly close?

Use the exact error message where possible. Say “the app closes” if it closes, or “the readings stop updating” if it stays open but shows old readings. These are different problems.

If readings are missing, tell us whether the manufacturer's app or the service you follow still shows current readings. If the problem is on a watch or widget, say whether the xDrip4iOS **Home** screen is still updating.

### Which phone and app versions are you using?

Include:

- your iPhone or iPad model and iOS or iPadOS version, found in the phone's **Settings > General > About**
- the xDrip4iOS version **and build number**, found in xDrip4iOS **Settings > About xDrip4iOS**
- how you installed xDrip4iOS, such as TestFlight or your own Xcode build
- the model of any other device affected, such as an Apple Watch.

“The latest version” is not specific enough. Different people may have different builds available. If you cannot find a detail, say so.

### When does it happen, and has it worked before?

Tell us whether this is a first-time setup or something that previously worked. Give the date and local time of a recent example, with your time zone or country and region.

Explain whether it happens all the time, occasionally, or only in a particular situation, such as when the phone is locked. If you can make it happen again, describe the steps.

Mention anything that changed shortly before the problem started, such as an app update, a new phone, a new sensor, or a changed setting. If nothing changed that you know of, say that.

### What have you tried, and what happened?

“I tried everything” does not tell us which checks have already been done. “I restarted the phone. Readings returned for ten minutes and then stopped again” gives us something useful to investigate.

It is fine to say you have not tried anything yet. Check the relevant [troubleshooting guide](index.md), but do not delete the app or remove a device just to prepare a help request. Record the problem before changing settings.

## An example

This gives people very little to work with:

> Libre isn't connecting. Can anyone help?

This gives them a useful starting point:

> I'm using a Libre 2 sensor and following its readings through LibreLinkUp in xDrip4iOS. It worked until this morning. LibreLinkUp shows a current reading, but xDrip4iOS still shows the reading from 08:15. Opening xDrip4iOS does not bring in new readings.
>
> My phone is [iPhone model], running [iOS version]. I have xDrip4iOS [version and build], installed through TestFlight. The problem started around 08:20 on [date], Spanish mainland time. I restarted the phone, but nothing changed. The attached screenshot shows the message I get.

Replace the details in brackets with your own information. A useful opening line also helps people recognise your setup, such as “Libre 2 through LibreLinkUp: readings stopped updating this morning”.

## Copy this if it helps

You can use this starting point or write the same information in ordinary sentences. Leave out details that do not apply, and say if you do not know an answer.

```text
My exact CGM or system:
How readings reach xDrip4iOS, including other apps or devices involved:
What I'm trying to do:
What happens instead:
My phone, iOS version, and xDrip4iOS version and build:
How I installed xDrip4iOS:
When it started, whether it worked before, and any recent changes:
What I've tried and the result:
Relevant screenshot or exact error message:
```

## Screenshots and the Activity Log

A screenshot of the relevant screen can help. Include a written explanation of what is wrong and when it happened. A screenshot alone may not show what you expected or how your system is set up.

The [Activity Log](activityLog.md) can provide useful supporting information about recent connections, readings, errors, and recoveries. Open **Settings > Troubleshooting > Activity Log** soon after the problem and note the time it happened. The log keeps up to the previous 24 hours, so useful details may no longer be available if you wait.

Use the copy button to copy the report, or the Share button to save or share it. The copied report includes app and setup information as well as the activity history. Searching only filters the on-screen list. Copying or sharing still includes the complete report.

Review screenshots and logs before posting them publicly. Remove personal or account details that are not needed. The Activity Log avoids passwords and access tokens, but it can still contain glucose values, timestamps, and other health-related information. Never post passwords, Nightscout API secrets, or access tokens.

### Detailed Issue Reports

An **Issue Report** is a separate developer tool. Use it only when an xDrip4iOS developer asks for one. You do not need to send one before asking for help.

When requested, open **Settings > Advanced Settings**, enable **Show**, then select **Issue Report**. Enable **Include Debug Level** only when requested and select **Send Issue Report** after reproducing the problem.

An Issue Report can contain device identifiers, service responses, and health information. Check the destination and attached files before sending. Do not post unreviewed trace files publicly. Copying or sharing the Activity Log does not attach these developer trace files.

## Keep the conversation moving

Keep updates in the same conversation so everyone can see what has already been tried. If someone asks several questions, try to answer each one. “I don't know” is a useful answer too. If a suggested step is unclear, ask for an explanation before trying it.

When you try a suggestion, tell us what changed, even if nothing changed. If you find a solution, add it to the conversation so the next person can benefit.

Replies depend on volunteers being available. Clear information makes it easier for someone to help, but it cannot guarantee an immediate answer. We do not expect technical expertise. We do need enough information to understand the problem.
