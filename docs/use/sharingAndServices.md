# Sharing and Services

The **Sharing and Services** section contains connections that send glucose information elsewhere or make it available to another app or person.

These services are separate from the current data source. A follower source brings readings into xDrip4iOS. A sharing service sends the readings that xDrip4iOS already has to another destination.

## Choose a service

- [Nightscout](../services/nightscout.md) sends glucose to a Nightscout site and can also provide treatment and AID information.
- [Dexcom Share](../services/dexcomShare.md) sends readings to the Dexcom Share service so approved followers can receive them. Its settings show account, connection, and upload activity separately.
- [Apple Health](../services/appleHealth.md) writes glucose readings to Apple Health on the same iPhone.
- [Calendar Share](../services/calendarShare.md) writes readings to a selected calendar. Another xDrip4iOS or Zukka user can follow the shared calendar.
- [Contact Image](../display/contactImage.md) updates a contact photo that can be shown by Apple's Contacts complication on Apple Watch.
- [OS-AID Share](../services/osAidShare.md) sends readings to a compatible AID app in a specially configured build.
- [Speak Glucose](../display/speakGlucose.md) reads glucose information through the iPhone audio system.
- [M5Stack](../connect/devices.md) controls the appearance and connection settings for a paired M5Stack or M5StickC display.

## Before sharing

Confirm that **Home** shows a current glucose value and timestamp before enabling another destination. Then check the service status, destination account, site, calendar, or device.

Each service has its own update timing. A current value on **Home** does not guarantee that another service has already received it. Check the timestamp at the destination when it is available.

Only enable the services you use. Glucose values, account names, calendar events, contact images, and AID information can be visible to other people or apps depending on the destination permissions.

## Sharing conflicts

Some combinations are intentionally prevented:

- Dexcom Share upload is disabled when Dexcom Share is the follower source.
- Calendar Share is unavailable when Shared Calendar is the follower source on the same device.
- Nightscout follower readings should not be uploaded back to the same Nightscout site.

These restrictions prevent the same readings from being sent back to their source. They do not stop you from sharing to a separate destination when the related guide says that setup is supported.
