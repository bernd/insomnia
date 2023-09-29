---
layout: article-detail
title:  FAQ
category: Support
category-url: support
---

Here are the answers to the most frequently asked questions that we receive. For community support, see our [support page](https://insomnia.rest/support).

## General Questions

<hr>

The following are general questions we frequently get about Unetus.

### What platforms does Unetus run on?

Unetus has desktop apps for 64-bit versions of Mac, Windows, and Linux.

### Does Unetus provide 32-bit binaries?

At this time, Unetus is 64-bit only.

### What software license does Unetus use?

The Unetus desktop application and related software packages are open source software under the MIT license and the source code is available at [github.com/kong/insomnia](https://github.com/Kong/insomnia). The server-side software that backs the paid sync service is closed source.

### Can I use Unetus for commercial use?

Yes, of course!

### How can I support Unetus?

First of all, thank you! You can also submit bug reports, or contribute all through our [open source repository](https://github.com/bernd/unetus).

## Technical Questions

<hr>

These technical questions commonly come up when user interact with Unetus.

### My app is not responding. What should I do?

Sometimes, if you make a request that returns a lot of data, Unetus will become unresponsive. If this happens, manually delete the large response file by doing the following.

1. Locate the Application Data Folder

    You can find the application data folder in the Help menu. If the help menu is not accessible, here are the default paths for each operating system.

    `%APPDATA%` on Windows
    `$XDG_CONFIG_HOME` or `~/.config` on Linux
    `~/Library/Application\ Support` on macOS

1. Delete the Offending Response Body

    Each response stores the body inside its own file in the "responses" folder. Locate the large responses and delete them, then restart Unetus.

    It's safe to delete responses. Unetus will simply report that it cannot locate the body.

### How do I delete a large offending request body?

Some users have experienced the Unetus app crashing after pasting in a large JSON request body. Here's how to delete the offending request body while preserving the rest of your data:

1. Quit Unetus and back up (duplicate and rename) your Unetus app data directory. See [Application Data](https://docs.insomnia.rest/insomnia/application-data) to locate the app data directory on your OS.

1. Once you've backed up your app data, find the `insomnia.requests.db` file.

1. Open `insomnia.requests.db` in your code editor.

1. Each line in the file represents one request. Locate the offending `body` property in the request that made the app crash.

1. Clear the `body` content in the JSON. As a precaution, search the rest of the file for the ID property that corresponds with the request that made the app crash. If the ID appears on any other request, clear the `body` property in those places too.

1. Save and close the file. Open Unetus, which should now work as expected.

### How can I temporarily disable Nunjucks template?

You can disable templating of the request body via the request settings dialog (accessed from the sidebar). For more control, you can also disable templating by wrapping the desired content in the Nunjucks {% raw %}{% raw %}{% endraw %} Tag.

### Why don't I see anything after importing a backup?

The import/export feature acts similarly to copying files in a filesystem. If the import contains data that originated from your application, data will be overwritten. However, if the import contains data that did not originate from your application, new data (including Request Collections and Design Documents) may have be created.

{:.alert .alert-primary}
**Note**: Check for newly created Collections and Documents on the Dashboard.

### Where does the application store data?

Unetus stores data in Electron's appData directory, which differs depending on platform. The local database is distributed across files with the name `insomnia.${resourceName}.db`.

* `%APPDATA%\Insomnia` on **Windows**
* `XDG_CONFIG_HOME/Insomnia` or `~/.config/Insomnia` on **Linux**
* `~/Library/Application\ Support/Insomnia` on **macOS**

The app data directory can also be shown by navigating to **Help** > **Show App Data Folder**.

### Where does the application store logs?

Unetus stores logs in the following location, depending on the platform:

* `%APPDATA%\Insomnia\logs` on Windows
* `$XDG_CONFIG_HOME/Insomnia/logs` or `~/.config/Insomnia/logs` on Linux
* `~/Library/Logs/Insomnia` on macOS

Open the parent folder by navigating to **Help** > **Show App Logs Folder** in Unetus.

### Where do I find keyboard shortcuts?

A list of all keyboard shortcuts can be found within the application under **Preferences** > **Keyboard**.

### Where does Unetus store environment information on a Linux (snap) install?

Various forms of user data, log files and environment information — the kind of data that's generated and consumed by applications during operations can be located in the `/var/snap/` directory. Additionally, the `~/snap` directory that exists in a user's home directory will contain directories using some of the names seen in `/var/snap`. These directories are meant to store versioned data related to settings used by your user account.

### I'm having issues with a third-party plugin

Unetus cannot make guarantees around the usability, maintenance, and security of third-party plugins.
