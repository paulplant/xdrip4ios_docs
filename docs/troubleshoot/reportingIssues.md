# Report a problem

A useful report identifies the build, data path, exact time, observed result, and expected result without exposing private data.

## Search first

Check the troubleshooting pages and existing issues for the same app version and source type. A manufacturer or cloud-service outage is not an xDrip4iOS code defect.

## Include

- xDrip4iOS version and build number from **Settings > About**
- iPhone or iPad model and system version
- installation method
- Master or Follower mode
- exact CGM device or Follower source
- the local time and time zone of the problem
- exact steps that reproduce it
- what appeared in the data source section at the bottom of **Home** and on the relevant connection screen
- relevant entries from **Settings > Troubleshooting > Activity Log**
- whether restarting the app or device changed the result.

Use screenshots with account names, URLs, identifiers, and glucose history removed when those details are not required.

## Activity Log

The [Activity Log](activityLog.md) contains useful history from up to the previous 24 hours. It can show connection and service failures, recoveries, accepted readings, alerts, sensor conditions, integration results, and relevant setting changes.

Open **Settings > Troubleshooting > Activity Log** soon after the problem. You can search the on-screen list without changing the report. Use the copy button for text that you can paste into a support request, or use the Share button to send or save the complete report.

The Activity Log is designed to exclude secrets and raw developer messages. It can still contain glucose values, timestamps, and other health-related context. Review it before posting it publicly.

## Trace files

Use an Issue Report only when an xDrip4iOS developer asks for one. Open **Settings > Advanced Settings**, enable **Show**, then select **Issue Report**. Enable **Include Debug Level** only when requested and select **Send Issue Report** after reproducing the problem.

An Issue Report can contain device identifiers, timestamps, service responses, and health information. Review the destination and the attached files before sending.

The Activity Log does not include or attach these developer trace files.

!!! warning
    Never publish passwords, Nightscout API secrets, access tokens, follower account details, App Group identifiers tied to a private build, or an unreviewed trace file in a public issue.

## Write a precise title

Use a title such as `Dexcom G7 remains scanning after update to build 4228` instead of `Bluetooth broken`. One report should describe one reproducible problem.
