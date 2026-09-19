# Treatments

Open **Settings > General > Treatments** to choose how xDrip4iOS estimates insulin on board and carbohydrates on board from recorded treatments.

These estimates are used only when the selected treatment source does not already provide the value.

## Insulin Type

Select the rapid-acting insulin that best matches the bolus treatments recorded in xDrip4iOS:

- `NovoRapid`
- `Fiasp`
- `Lyumjev`.

The selected model estimates how much bolus insulin remains active. Basal insulin and basal injections are not included in this IOB estimate.

## Carb Duration

Select how long recorded carbohydrates should remain active. The available choices are 2 to 8 hours.

- 2 or 3 hours uses a faster absorption estimate.
- 4 to 6 hours uses a normal absorption estimate.
- 7 or 8 hours uses a longer absorption estimate.

The longer choices may be useful when digestion is slower, including for some people who use GLP-1 medication. This setting changes an estimate. It does not measure actual absorption.

## When the settings are automatic

If Nightscout supplies IOB and COB from an AID system, both settings show **Automatic** and cannot be changed.

If CareLink supplies IOB, **Insulin Type** is automatic. **Carb Duration** remains available so xDrip4iOS can estimate COB from recorded carbohydrate treatments.

xDrip4iOS does not switch to a local estimate during a temporary outage from the selected online source. This avoids replacing an AID value with a different calculation.

## Where the values appear

Available IOB and COB values appear in the compact therapy area on **Home**. Select a locally calculated value to see that it is an estimate and review the setting used.

Enable **Show IOB/COB** under **Settings > General > Home Screen** or **Quick Show/Hide** to add the curves to the main chart.

Live Activity settings have a separate **Show IOB/COB** option. It controls the Large Lock Screen layout and the CarPlay or Smart Stack Chart layout.

!!! note
    Local IOB and COB are estimates based on the treatments stored in xDrip4iOS and the current settings. They are not pump calculations, they are not sent to an AID system, and they are not added to the clinical report as AID history.
