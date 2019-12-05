# Prerequisites
Before we begin, download the following files if you do not already have them.
- [Advanced Combat Tracker](https://advancedcombattracker.com/includes/page-download.php?id=56) - If ACT is not installed, run the setup before proceeding with anything else.
- [FFXIV ACT Plugin](https://github.com/ravahn/FFXIV_ACT_Plugin/releases/download/2.0.4.5/FFXIV_ACT_Plugin_2.0.4.5.zip)
- [Cactbot Plugin](https://github.com/quisquous/cactbot/releases/download/v0.13.2/cactbot-0.13.2.zip)
- [Overlay Plugin](https://github.com/ngld/OverlayPlugin/releases/download/v0.11.2/OverlayPlugin-0.11.2.zip)

# Extracting plugins
NOTE: This guide assumes ACT is installed in the default location of `C:\Program Files (x86)\Advanced Combat Tracker`. Within said folder, create a folder called `plugins` if it does not already exist. We will extract the plugins to that directory.

For all but the Cactbot plugin, we will create a folder under `C:\Program Files (x86)\Advanced Combat Tracker\plugins\` to keep things tidy.

## FFXIV ACT Plugin
Create the folder `FFXIV_Plugin` under `C:\Program Files (x86)\Advanced Combat Tracker\plugins`. Extract `FFXIV_ACT_Plugin_2.0.4.5.zip` to the newly created folder.

## Overlay Plugin
Create the folder `Overlay` under `C:\Program Files (x86)\Advanced Combat Tracker\plugins`. Extract `OverlayPlugin-0.11.2.zip` to the newly created folder.

## Cactbot Plugin
Unlike the previous plugins, Cactbot contains a parent folder meaning we don't need to create one. Extract `cactbot-0.13.2.zip` to `C:\Program Files (x86)\Advanced Combat Tracker\plugins`. 

Skip to the next paragraph if you are not an advanced user. For advanced users, the zip will generate an extra folder depth; you're welcome to fix this by drilling down one folder level in the archive and then extract so your folder structure is `cactbot\files.dll` instead of `cactbot-0.13.2\cactbot\files.dll`.

Navigate to `C:\Program Files (x86)\Advanced Combat Tracker\plugins` and rename the folder `cactbot-0.13.2` to `cactbot`. You will effectively have a folder structure such as `cactbot\cactbot`.

# Configuring ACT Plugins
Open ACT. You may or may not receive a prompt asking if you wish ACT to unblock DLL files; if so, say yes. If prompted with the Setup Wizard (only upon first launch of ACT), accept the default configuration.

- Click on Plugins > Plugin Listing.
  
  ![Plugins](https://raw.githubusercontent.com/quisquous/cactbot/master/screenshots/install_cactbot_add_plugin.png)
- Click browse and navigate to `C:\Program Files (x86)\Advanced Combat Tracker\plugins`. 
- For each of the below, select the respective DLL file and click 'Add/Enable Plugin'.
  - FFXIV ACT Plugin: `FFXIV_Plugin\FFXIV_ACT_Plugin.dll`
  - Overlay Plugin: `Overlay\OverlayPlugin.dll`
  - Cactbot Plugin: `cactbot\cactbot\CactbotOverlay.dll`
- Ensure the order looks like the image below.
![](https://raw.githubusercontent.com/quisquous/cactbot/master/screenshots/install_cactbot_plugin_order.png)
- Close Advanced Combat Tracker and reopen it to load the plugins.
- Under Overlayplugin.dll tab, click **New** to create a new overlay with the following configuration:
  - **Name**: *Cactbot*
  - **Type**: *MiniParse*.
- For URL, click `...` and browse to `C:\Program Files (x86)\Advanced Combat Tracker\plugins\cactbot\cactbot\ui\raidboss`. You have a few choices, of which I recommend the first option. Select the HTML file that works for you.
  - **raidboss.html** - Display both the timeline and alerts (such as debuffs or important mechanics). Highly recommended.
  - **raidboss_alerts_only.html** - No timeline, only alerts. Would not recommend.
  - **raidboss_timeline_only.html** - Timeline only, no alerts.
- After selecting the appropriate HTML file, an overlay will appear. Adjust the position and size as desired. Once satisfied, set a checkmark on **Enable clickthru** and **Lock overlay** in Overlayplugin.dll tab to hide the setup window.
- NOTE: this test will trigger various alert sounds so ensure your volume is not cranked up. To test, teleport to Summerford Farm in La Noscea and initiate a countdown with `/cd 5`. It will popup a mock timeline and show various alerts. If it appears, it is working properly.
- If you wish to adjust the loudness of the alert sounds, you can try to adjust **WAV Vol** under Options tab > Sound Settings.