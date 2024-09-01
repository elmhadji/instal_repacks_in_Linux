# How to Install FitGirl or DODI Windows Repacks on Linux using Lutris

## Table of Contents
1. [Introduction](#introduction)
2. [What is Lutris?](#what-is-lutris)
3. [Setting Up Lutris](#setting-up-lutris)
4. [Configuring Lutris](#configuring-lutris)
5. [Installing Different Wine Versions](#installing-different-wine-versions)
6. [Choosing a Wine Version for Lutris](#choosing-a-wine-version-for-lutris)
7. [Installing Windows Repacks in Lutris](#installing-windows-repacks-in-lutris)
8. [Running the Installer](#running-the-installer)
9. [Post-Installation Steps](#post-installation-steps)
10. [Troubleshooting](#troubleshooting)

## Introduction
- **Note**: This guide does not cover unarc.dll and ISDone.dll errors encountered during the installation of Windows repacks.
- **Note**: This guide also does not address issues with running cracked Windows games on Lutris.
- **Contains**: Best practices for installing cracked Windows games on Linux using Lutris.

## What is Lutris?
[Lutris](https://lutris.net/about) is a game manager that allows you to easily install and run Windows games on Linux. While there are other programs that can do this, Lutris is preferred for its flexibility and support for various game sources, including repacks.

## Setting Up Lutris
1. **Download and Install Lutris**: Follow the [installation instructions](https://lutris.net/downloads) for your Linux distribution.
2. **Install Wine and Dependencies** (if not using Flatpak or on a Steam Deck):
   - Follow [this guide](https://github.com/lutris/docs/blob/master/WineDependencies.md) to install a recent version of Wine and its dependencies.
3. **Install Proper Drivers**: For detailed instructions, refer to [this guide](https://github.com/lutris/docs/blob/master/InstallingDrivers.md).

## Configuring Lutris
1. **Open Lutris**: If it's your first time running Lutris, wait a few minutes for setup.
2. **Access Preferences**:
   - Click the hamburger menu in the top right corner and select "Preferences."
3. **Global Options**:
   - Enable "Show advanced options" in the bottom left corner.
   - Set "Disable Lutris Runtime" to "Disabled."
   - Enable "Disable Desktop effects" and "Disable Screen Saver" for better performance.
   - Enable "Feral Gamemode" for improved performance. (If grayed out, install the "gamemode" package using your distro's package manager.)
   - Click "Save" to apply the changes.

## Installing Different Wine Versions
Wine is a compatibility layer that allows Windows games to run on Linux. Various Wine versions are available:

- **wine** and **wine-staging**: Official builds, with staging preferred for gaming.
- **[Proton](https://github.com/ValveSoftware/Proton/)**: A compatibility layer based on Wine, built by Valve for Steam games.
- **[Lutris Wine](https://github.com/lutris/docs/blob/master/WineBuilds.md#lutris)**: Customized versions by the Lutris team, with patches and improvements from Proton.
- **[Proton-GE](https://github.com/GloriousEggroll/proton-ge-custom)**: A popular fork with bleeding-edge components for improved compatibility.
- **[Wine-GE](https://github.com/GloriousEggroll/wine-ge-custom)**: A fork similar to Proton-GE but without components like DXVK, intended for non-Steam games.

### Methods to Install Wine Versions
1. **Through Lutris**:
   - Hover over the "Wine" button on the left panel under "Runners" and click the download icon.
   - Choose a Wine build, click "Install," and then "OK" when done.
2. **Using [ProtonUp-Qt](https://github.com/DavidoTek/ProtonUp-Qt)** (Recommended):
   - Download ProtonUp-Qt via AppImage, Flathub, or from the AUR if using Arch. [Download Instructions](https://github.com/DavidoTek/ProtonUp-Qt#protonup-qt)
   - Open ProtonUp-Qt, select "Lutris" from the drop-down menu, and click "Add version."
   - Choose and install your desired Wine version (non-lol version recommended).
   - Restart Lutris if it was open.

## Choosing a Wine Version for Lutris
- **Recommended Version**: Use Wine-GE, which includes all Proton patches and is frequently updated.
- **Avoid using Proton-GE with Lutris**: More info [here](https://www.reddit.com/r/linux_gaming/comments/w0vfn1/another_protonge_vs_winege_thread/) and [here](https://github.com/GloriousEggroll/proton-ge-custom#1-running-non-steam-games-with-proton-outside-of-steam-is-not-supported-do-not-ask-for-help-with-this).

### To Install Wine-GE in Lutris Using ProtonUp-Qt:
1. Open ProtonUp-Qt.
2. Select "Lutris" from the drop-down menu.
3. Click "Add version."
4. Select "Wine-GE" under "Compatibility tool."
5. Choose the latest non-lol version and click "Install."
6. Restart Lutris if it was open.

## Installing Windows Repacks in Lutris
1. Open Lutris.
2. Click on the '+' icon in the top left corner.
3. Click "Add locally installed game."
4. Enter the name of your game in the "Name" field.
5. Select "Wine (Run Windows games)" from the "Runner" list.
6. Go to the "Game options" tab and enable "Show advanced options."
7. Leave the "Executable" field empty for now.
8. In the "Wine prefix" field, enter the path where you want to create the prefix (e.g., `~/Games/spider-man`).

## Running the Installer
1. Click on the game you just added.
2. Click the "Up" icon next to the "Wine Glass" icon on the bottom panel.
3. Select "Run EXE inside Wine prefix."
4. Choose the "setup.exe" file from the repack folder and run it.
5. Follow the installer instructions, ensuring you install the game on the "C:\" drive within the Wine prefix.

## Post-Installation Steps
1. Right-click on the game and select "Configure."
2. Go to the "Game Options" tab and click "Browse" next to the "Executable" field.
3. Navigate to the game's .exe file within the prefix folder and select it.
4. Double-click your game to launch it.

## Troubleshooting
- **Unarc.dll or ISDone.dll errors**: If you encounter these, consider using DODI's repacks instead of FitGirl's, as they tend to be more reliable.
