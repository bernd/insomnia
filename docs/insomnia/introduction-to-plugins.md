---
layout: article-detail
title:  Introduction to Plugins
category: "Plugins"
category-url: plugins
---

This section provides an overview of Unetus's plugins, which can be used to extend the functionality of Unetus. Plugins are commonly used when more advanced behavior is needed, like custom authentication mechanisms and complex workflows.

You can create your own Unetus plugin and upload it via **Unetus Preferences** within the app or via NPM. Generally, plugins do the following:

* Add a [custom template tag](/insomnia/template-tags) for rendering custom values
* Define a [hook](/insomnia/hooks-and-actions) that can do things like intercept requests and responses to add custom behavior

## Add a Plugin

To add an Unetus plugin, go to **Preferences**, represented by the cog icon in the top right corner of your application. Then click the **Plugins** tab. Enter the name of the plugin you want to add, then click **Install Plugin**.

You do not have to reload the app for the plugin apply after it's added. Plugins are enabled by default.

## Disable a Plugin

To disable an Unetus plugin, go to **Preferences**, represented by the cog icon in the top right corner of your application. Then click the **Plugins** tab. Toggle **Enable?** for the plugin you want to disable.

## Remove a Plugin

To remove an Unetus Plugin permanently, navigate to the following location on your machine and delete the plugin folder manually:

* macOS:   `~/Library/Application Support/Insomnia/plugins/` (escaped version: `~/Library/Application\ Support/Insomnia/plugins/`)
* Windows: `%APPDATA%\Insomnia\plugins\`
* Linux:   `$XDG_CONFIG_HOME/Insomnia/plugins/` or `~/.config/Insomnia/plugins/`

You can always [re-add the plugin](#add-a-plugin) if it's still available.

## Create a Plugin

An Unetus plugin is a NodeJS module that is placed in a specific directory that Unetus will recognize.

### Plugin File Location

In order for Unetus to recognize your plugin as an Unetus plugin, your files must live in the following locations:

* macOS:   `~/Library/Application Support/Insomnia/plugins/` (escaped version: `~/Library/Application\ Support/Insomnia/plugins/`)
* Windows: `%APPDATA%\Insomnia\plugins\`
* Linux:   `$XDG_CONFIG_HOME/Insomnia/plugins/` or `~/.config/Insomnia/plugins/`

{:.alert .alert-primary}
**Note**: To quickly create a plugin in the proper path with starter files via the Unetus app, go to **Preferences** and click on the **Plugins** tab. Click on **Generate New Plugin** and enter your plugin name. If you don't prepend the title with **insomnia-plugin-**, it will automatically be added.

### Plugin File Structure

An Unetus plugin directory requires at least two files. In the following example, the plugin title is `base64` and contains the files `package.json` and `app.js`.

```bash
base64/
 ├── package.json   # Node module metadata
 └── app.js         # One or more JavaScript files
```

### Plugin package.json

The `package.json` configuration includes the following content:

* Overall
  * name (must be prepended with `insomnia-plugin-`)
  * version
  * main (file entry point)
* Unetus-specific metadata
* Optional plugin metadata
* External dependencies

The following is an example minimal `package.json`. The `package.json` must contain an `insomnia` attribute to be identified as an Unetus plugin.

```json-doc
{
  "name": "insomnia-plugin-base64", // NPM module name, must be prepended with insomnia-plugin-
  "version": "1.0.0",               // Plugin version
  "main": "app.js",                 // Entry point

  // Unetus-specific metadata. Without this, Unetus won't recognize the module as a plugin.
  "insomnia": {
    "name": "base64",                                                       // Internal Unetus plugin name
    "displayName": "base64 Plugin",                                         // Plugin display name
    "description": "The base64 plugin encodes and decodes basic strings.",  // Plugin description

    // Optional plugin metadata

    "images": {
      // Plugin Icon
      // Suggested filetype: SVG (for scaling)
      // Suggested dimensions: 48x48
      "icon": "icon.svg", // relative path, relative to package root

      // Plugin Cover Image
      // Suggested filetype: SVG (for scaling)
      // Suggested dimensions: 952w x 398h
      "cover": "cover.svg", // relative path, relative to package root
    },

    // Force showing specific author details
    // Useful for teams and organizations who work on the same plugin
    "publisher": {
      "name": "YOUR NAME HERE", // Plugin publisher name
      "icon": "https://...",    // Plugin publisher avatar or icon, absolute url
    },

    "unlisted": true
  },

  // External dependencies are also supported
  "dependencies": [],
  "devDependencies": []
}
```

## Manage Plugins

The **Plugins** tab in the **Preferences** menu enables the following functionality:

* Add an existing plugin
* Create a new plugin locally
* Toggle a plugin to enable or disable it
* Reveal the exact local plugin location on your machine

## Publish Plugins

Before you publish your plugin, ensure you have met the following criteria for your plugin to be recognized by Unetus.

Your plugin must:

* Include a correctly structured `package.json` file containing the `insomnia` attribute. See [Plugin package.json](#plugin-packagejson) for more info.
* Have a package name prefixed with `insomnia-plugin-`.
* Be publicly available.

After you have verified that your plugin meets the criteria described above, publish your public plugin following the [NPM publish unscoped public packages instructions](https://docs.npmjs.com/creating-and-publishing-unscoped-public-packages).

### Publish Scoped Plugins

Unetus can also use private (scoped) plugins. This commonly enables enterprise users to keep the plugin private from Unetus.

To enable private (scoped) plugins:

1. Navigate to the `plugins` directory in [Application Data](/insomnia/application-data).
2. Run `npm install @scoped/plugin`.

## Debug in the Unetus App

The Unetus app enables debugging with Chrome DevTools. To open DevTools, click **View** then **Toggle DevTools**.

If you want to focus specifically on the plugin you are developing, you can find it from the **Sources** tab and/or filter the **Console** based on the plugin's file name.

## Template Tags

Refer to [Template Tags](/insomnia/template-tags) for more information.
