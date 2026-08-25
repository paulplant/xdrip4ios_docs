# Glucose Readings

The glucose reading list shows current and older readings with the details supplied by the data source.

Select **Glucose Readings** in the toolbar at the top of **Home**. Select a reading to see its stored information.

## Reading list

Use the date control to inspect another day. The list loads the most recent 14 days of readings. Older stored history remains available to charts, statistics, reports, and Data Management.

Each row shows the displayed glucose, unit, trend arrow, time, and glucose-range colour. A small dot beside the time marks a reading that arrived later after a connection gap.

Use the arrow button after scrolling down to return to the newest reading for the selected day.

## Glucose Reading

The stored information can include:

- source device name, glucose range, and timestamp
- whether the reading arrived after a connection gap and when it was added
- trend arrow and change per minute or per five minutes
- calibration information used for that reading
- raw, calibrated, adjusted, smoothed, and final glucose values
- the internal reading identifier.

Fields that are not supplied by the selected source remain absent or show that no value is available.

## Readings received after a gap

Some CGM devices send missing readings after they reconnect. A dot beside the reading time marks a reading that arrived later. Select the reading to see when it was added. The reading time remains the time when the measurement was made.

Old readings received after a gap do not trigger every alert that might have occurred when they were measured.

## Delete readings

Swipe a reading to delete it. To delete several readings from the selected day, select **Edit**, choose the readings, and then select the delete button.

Deleting removes the readings from local history. If they also exist on the configured Nightscout site, xDrip4iOS requests their deletion from Nightscout.

!!! warning
    Deleted glucose readings cannot be restored unless they are available in a backup or can be imported again. Deleting readings changes charts, statistics, and reports.
