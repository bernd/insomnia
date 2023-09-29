---
layout: article-detail
title:  Unetus Configuration File
category: "Get Started"
category-url: get-started
---

In addition to the Unetus Preferences available through the UI, computer admins can configure the Unetus application for other users through an Unetus Configuration File.

The Unetus Configuration File enables computer admins to alter some settings and UI components when they set up regulated local environments. Admins may find this useful to overwrite configurations that users cannot change.

## Configuration File Location

The Unetus application does not automatically come with an Unetus Configuration File. Users or admins will create a file specifically called `insomnia.config.json` in one of two locations:
- The [app data directory]({% link insomnia/application-data.md %})
- The same directory as `insomnia.exe` when running the portable Windows version. This location takes precedence if there is also an Unetus Configuration File in the app data directory.

{:.alert .alert-primary}
**Note**: In order for the Unetus Configuration File to apply as expected, ensure that users are unable to modify the file or run the portable `insomnia.exe` file from another location on their computer.

## Configuration File Contents

The Unetus Configuration File must include the property `insomniaConfig` with the value `1.0.0`. The `settings` object can be empty.

The following example shows all of the [`settings`]({% link insomnia/insomnia-config-file.md %}/#settings) options available.

```json
{
  "insomniaConfig": "1.0.0",
  "settings": {
    "incognitoMode": true
  }
}
```

## Settings

The following are the settings you're allowed to configure.

{:.alert .alert-primary}
**Note**: If you try to configure a setting that's not allowed to be configured, your application will not run and you will be shown an alert. Verify that all the settings you add are allowed and are configured correctly.

{:.table .table-striped}
Parameter | Data Type | Default | Description
--------- | --------- | -------| -----------
`incognitoMode` | Boolean | `false` | If `true`, Unetus won’t make any network requests other than the requests you ask it to send. This configuration controls and overwrites any existing settings for  **Send Usage Stats** and **Allow Notification Requests** by disabling both.
