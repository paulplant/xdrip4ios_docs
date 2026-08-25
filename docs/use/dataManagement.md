# Data Management

Data Management controls local storage, backups, Nightscout history import, data retention, and permanent deletion.

Open **Settings** and scroll to the **Data Management** section.

## Storage Info

**Storage Info** shows how much local storage is used, the number of stored items, and the earliest and latest stored dates. Pull down to refresh the values.

The storage size might not become smaller after old data is removed. The app can reuse the available space.

## Create Backup

Select **Create Backup**, then choose whether to include:

- app settings and alarms
- glucose readings
- treatments.

Stored Nightscout AID history and profiles are included automatically when glucose readings or treatments are selected.

Enable **Encrypt Backup** to protect the file with a password. An encrypted backup can also include account details for Nightscout, Dexcom Share, LibreLinkUp, Medtrum EasyView, CareLink, and M5Stack.

Enter and confirm the password, then select **Create and Share Backup**. Save the `.xdripbackup` file in a location that will still be available if the device is lost or replaced.

!!! important
    xDrip4iOS cannot recover a forgotten backup password. Keep it in a safe place. Do not send an unencrypted backup through a service that you do not trust.

## Restore Backup

Select **Restore Backup** and choose a `.xdripbackup` file. You can also open the backup file from the Files app, Mail, or another app that received it.

Enter the password if the backup is encrypted. Review its date and contents, then choose how historical data is handled:

- **Keep Current Data** keeps existing local history and adds records that are not already stored.
- **Fill Gaps** adds historical records where local history is missing.
- **Replace Backup Range** deletes local glucose readings, treatments, and AID history within the backup period before restoring them.
- **Ignore Data** does not restore historical data.

App settings, alarms, and account details have separate restore controls. Account categories can be selected individually when the encrypted backup contains them.

Restoring CareLink account details restores any saved username and password, the region, and the selected patient. The username and password are optional and only pre-fill Medtronic's login page. You may still need to complete the CareLink login again before readings resume.

!!! warning
    **Replace Backup Range** permanently replaces local history within the dates covered by the backup. Review the backup summary and date range before confirming.

After a restore, open **Home** and check the current data source, glucose unit, glucose ranges, alerts, and sharing services.

## Import Data

Select **Import Data > Nightscout** to import glucose readings, treatments, and **Device Status** from the Nightscout site configured under **Settings > Sharing and Services > Nightscout**.

**Device Status** contains historical AID information used for Looping status on **Home**, landscape charts, and reports. Select it when this history is required.

Choose the required data and period, then select **Import from Nightscout**. Keep xDrip4iOS open until it finishes. Existing local data is kept and matching records are skipped.

An interrupted import can be resumed from its last saved point. Discarding a saved import removes its saved progress. Readings and treatments that were already imported remain stored.

The import period is limited by the current data-retention setting.

## Manage Data

### Data Retention

**Automatic Housekeeping** removes glucose readings, treatments, AID history, and unused calibrations older than the selected period. It runs at most once per day when the app opens.

Disable it if you want to remove data only through **Data Deletion**.

### Data Deletion

**Data Deletion** can remove glucose readings, treatments, and Device Status while keeping recent data, using a selected date range, or deleting all selected history.

The app shows the number of items that will be removed before asking for a six-digit confirmation code. Nothing is deleted until the final confirmation.

!!! warning
    Data Deletion cannot be undone. Create a backup first if you might need the selected history later.
