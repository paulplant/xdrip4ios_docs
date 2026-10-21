# Advanced Settings

**Advanced Settings** contains specialised options that are not needed for normal use.

Enable **Show** to reveal the additional options. They hide again automatically after a short period. Their saved values do not change when the rows are hidden.

**Issue Report** opens the developer reporting screen. Enable **Include Debug Level** only when requested, then select **Send Issue Report**. Do not send an Issue Report unless an xDrip4iOS developer asks for one.

For normal troubleshooting, use **Settings > Troubleshooting > Activity Log**. It contains clear recent events that can be copied or shared without including the private developer trace files used by an Issue Report.

## Documentation and display

- **Translate Documentation** opens online help in the app language when a translation is available. English opens the original documentation.
- **StandBy Night Mode** allows the high-contrast night layout in StandBy.
- **StandBy Big Numbers** forces the large-number StandBy layout.

## Frequent readings

Some sources can provide readings more often than every five minutes.

- **Frequent Nightscout Uploads** allows those additional readings to be uploaded instead of limiting uploads to the normal five-minute interval.
- **Frequent HealthKit Writes** allows the additional readings to be stored in Apple Health.

Most users should leave both settings disabled. More frequent data increases storage, network use, and the chance of duplicate-looking entries in another service.

## Connection and account options

- **Suppress Unlock Payload** changes the Libre 2 direct connection for a specialised parallel-app setup. Do not enable it during normal Libre 2 setup.
- **Libre 3 Credentials** shows the downloaded connection credential versions used for Libre 3 and Libre 3 Plus setup. The current version downloads automatically before the first NFC scan. Select another version only when support asks you to do so.
- **LibreLinkUp version** changes the version sent to the LibreLinkUp service. An incorrect value can cause login problems or an account restriction. Change it only when instructed.
- **CareLink version** changes the app version used for CareLink requests. Enter the exact `0.0.0` value supplied by support. An incorrect value can stop CareLink downloads.
- **CAGE Max Hours** changes when imported cannula information is shown as expired. Enter `0` to restore the default.

## Logging

**NSLog** and **OSLog** increase the diagnostic information produced by the app. Enable only the option requested for a problem report, reproduce the problem, then disable it again.

OS-AID sharing has its own page under **Settings > Sharing and Services > OS-AID Share**. Its delay schedule and warned sharing options are explained in [OS-AID Share](../services/osAidShare.md).

Change an advanced setting only when you understand its purpose or when a support instruction identifies the exact option. Record the previous value before changing it.
