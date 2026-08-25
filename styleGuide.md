# Documentation style guide

## Audience and language

Write for a person who uses a CGM but might not understand software terminology. Use short, direct sentences. Define a technical term before using it. Use the same term consistently.

Assume that the reader knows how to use an iPhone. Do not explain ordinary actions such as opening a tab, selecting a visible button, or returning to the previous screen unless the location could be unclear. Prefer a short path and one expected result over a list of micro-steps. Keep detail when the order matters, an action changes stored data, or a device has an unusual requirement.

Describe the interface from the user's point of view. Do not expose Swift identifiers, camelCase names, model names, or internal component names. When referring to information or a control, identify where the user can find it, such as **Settings > Data Source** or “the data source section at the bottom of the **Home** screen.” Avoid location-free phrases such as “the status row,” “the detail screen,” or “the data source status.” Use an exact app label only when the user can see that label in the released interface.

A page for a specific screen must use the exact English screen title in its heading and navigation entry. Its filename must be the lower camelCase form of that title, such as `glucoseAdjustments.md` or `speakGlucose.md`. Do not replace a visible screen title with an internal feature name or a broader technical description.

Explain what the user must do and what result to expect. Do not explain ownership, data flow, packets, processing paths, service endpoints, app state, or other implementation details unless the reader must know them to complete the task. Replace developer terms with visible behaviour. For example, write “Keep the Medtrum app running in the background and receiving readings” instead of describing which component owns the sensor connection.

Do not use semicolons, em dashes, or en dashes. Split the text into short sentences instead. Avoid stock phrases, filler, and promotional language. Write each sentence as a direct explanation or instruction.

The English text is the source for automatic translation. To keep it translatable:

- use literal wording rather than idioms, humour, or cultural references
- avoid sentences that depend on an image for their meaning
- do not join alternatives with a slash when a complete phrase is clearer
- keep one instruction in each numbered step
- identify an app or operating-system location before naming a control
- use bold text for screen names and `inline code` for exact labels shown in the app
- do not put important text inside an image.

Use **xDrip4iOS** for the project and app name. Use **iPhone**, **iOS**, **Apple Watch**, **Master**, **Follower**, **Bluetooth**, **Nightscout**, **Dexcom Share**, and **LibreLinkUp** with this spelling.

Use **Loop** only for the Loop app, an exact visible app label, or automated insulin delivery. Describe circular uploads as duplicate uploads or as sending readings back to the same site.

## Page structure

Start each page with one sentence that states its purpose. Put prerequisites before steps. Put expected results after steps. End with the most relevant troubleshooting link when a setup can fail.

Use admonitions consistently:

- `warning` for a safety risk or an action with destructive consequences
- `important` for a requirement that commonly blocks setup
- `note` for behaviour that explains a result
- `tip` for an optional shortcut.

The **Use the app** navigation follows the visible app structure. Every main tab has a stable entry page in `docs/use/`: `home.md`, `treatments.md`, `statistics.md`, `devices.md`, and `settings.md`. In-app help links should point to these pages.

Place Home toolbar screens below Home in the navigation. Place the top-level Settings sections below Settings in the same order as the app. Give every screen or section its own Markdown page so it can be moved without splitting content from another page. A parent group can use an overview page as its first entry.

## Screenshot standard

### Capture environment

Use the current xDrip4iOS source and an iPhone 17 Pro simulator unless the screen is specific to another device. Use:

- English app and system language
- dark appearance, matching the app
- the same simulator model, iOS version, text size, and display zoom
- a clean 9:41 status bar when practical
- glucose history can be shown when it does not identify a person
- no real names, Nightscout URLs, account details, passwords, or tokens
- transmitter IDs can be shown, but changing one character is preferred when the exact ID is not important.

Full-screen captures must include the complete app screen but not the macOS Simulator window frame. Do not crop full-screen captures to different aspect ratios.

### File layout and names

Store images below `docs/img/screenshots/`:

```text
docs/img/screenshots/
  source/       unedited simulator captures
  annotated/    images used when callouts are required
  detail/       standardised crops used when a full screen is unreadable
```

Use lower camelCase names, matching Swift naming style:

```text
<area><screen><state>.png
```

Examples:

```text
homeMainMaster.png
devicesAddCategory.png
settingsDataSourceFollower.png
```

An annotated image keeps the source name and adds `Annotated`. A crop adds `Detail<Subject>`.

### Annotation style

Use the xDrip4iOS yellow accent for outlines and arrows. Add a dark translucent backing when yellow would have insufficient contrast. Use numbered circular callouts when a page explains more than one item. Keep callout numbers in reading order, from top to bottom. Use an arrow only when an outline cannot identify the control clearly.

Do not add explanatory sentences to the image. Put the matching numbered explanations in Markdown so they can be translated and read by assistive technology.

### Display in Markdown

Use meaningful alt text that describes the screen and the highlighted control. Show full iPhone screenshots at a consistent width through the shared CSS. Place a screenshot immediately after the paragraph or step that introduces it.

Use screenshots for orientation and complex flows. Do not add a screenshot for every tap. The written instructions must remain complete when images are unavailable.

## Screenshot update checklist

Before committing a screenshot:

1. Confirm that it matches the released app interface.
2. Confirm that no personal or secret data is visible.
3. Confirm that the filename follows the convention.
4. Confirm that its dimensions match other images of the same type.
5. Confirm that annotations use the standard colour and numbering.
6. Confirm that the alt text explains the image.
7. Keep the unedited source capture when an annotated or cropped derivative is committed.
