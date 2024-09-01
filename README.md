# How to install FitGirl or DODI Windows repacks in Linux using Lutris.

- `NOTE`: This guide does not deal with unarc.dll and ISDone.dll errors that comes with installing Windows repacks.
- `NOTE`: This guide also does not deal with problems RUNNING quacked Windows games with Lutris
- `CONTAINS`: This guide will discuss habits or "best practices" that I have developed over the years of using Lutris to INSTALL quacked Windows games on Linux.

## [What is Lutris?](https://lutris.net/about)
Why Lutris: Installing Windows repacks on Linux is, lets just say unconventional for a Windows user and Lutris allows you to (If you know what you are doing) easily install and run Windows games on Linux. Their are other programs that also allow you to do that but I exclusively use Lutris to play games on Linux, so I have more experience and a greater understanding of Lutris, so I prefer Lutris.

## Setting Up Lutris:

1. Download and install Lutris. Installation instruction for different distros can be found [here.](https://lutris.net/downloads)
2. (Steam Deck owners skip to next heading and this step is not needed if you are running Lutris from Flatpak) As stated on the [download page](https://lutris.net/downloads) for Lutris, for a smoother experience install a recent version of Wine and its dependencies, just follow [this](https://github.com/lutris/docs/blob/master/WineDependencies.md) guide.
3. (Steam Deck owners, I said go away) Make sure you have proper drivers installed. For a detailed instructions follow [this](https://github.com/lutris/docs/blob/master/InstallingDrivers.md) guide.

## Actually Setting Up Lutris:

1. Open Lutris, if this is your first time running Lutris then you might have to wait for a couple of minutes for Lutris to set everything up.
2. Click on the hamburger menu button on the top right corner, just to the left of the minimize button, then click on "Preferences".
3. Click on "Global Options" and make sure these options are set as described:
	1. Enable "Show advanced options" in the bottom left corner of the window.
	2. "Disable Lutris Runtime" -> "Disabled" (You can read more about Lutris Runtime [here](https://github.com/lutris/docs/blob/master/LutrisRuntime.md))
	3. "Disable Desktop effects" and "Disable Screen Saver" -> "Enabled" (For slightly better performance)
	4. "Enable Feral Gamemode" -> "Enabled" also for better performance (If this option is grayed out then you will need to install the "gamemode" package in your system using your distro's package manager)
	5. Click on "Save" to save the changes.

## Installing different Wine versions:
##########################################################################

Wine is a compatibility layer that allows you to play Windows games on Linux and it has different versions like

- wine and wine-staging official build of Wine built by Wine themselves (staging is prefered for gaming)
- [proton](https://github.com/ValveSoftware/Proton/) is a compatibility layer based on Wine that is built by Valve which includes patches for different Steam games
- [lutris](https://github.com/lutris/docs/blob/master/WineBuilds.md#lutris) and [lutris-fshark](https://github.com/lutris/docs/blob/master/WineBuilds.md#lutris-fshack) (fshark might be depreciated after [Lutris Wine 7.2-2](https://github.com/lutris/wine/releases/tag/lutris-wine-7.2-2)) build by Lutris team and contains patches and improvement from Proton
- [proton-ge](https://github.com/GloriousEggroll/proton-ge-custom) is a full fork of proton build by [GloriousEggroll](https://github.com/GloriousEggroll) that contains the most recent bleeding-edge Proton and other components like dxvk, vkd3d etc and is very popular in the community and
- [wine-ge](https://github.com/GloriousEggroll/wine-ge-custom) also a fork of most recent bleeding-edge Proton that does not contain components like dxvk, vkd3d and more which is provided by Lutris and is meant to be used for non-steam games outside Steam like Lutris.

Their are other Wine versions that I have not listed here but this is all the information we will need for this guide. For more info about other Wine builds read [this](https://github.com/lutris/docs/blob/master/WineBuilds.md).

##########################################################################

Their are two methods to install different Wine versions:

1. Through Lutris itself:
	1. Hover your mouse over the "Wine" button on the left side panel of Lutris main window under "Runners", then a download icon should appear on that button, then click on the download icon.
	1. Choose a Wine build then click "Install" to install your chosen version and then click "OK" after the installation is done to exit out of the window.
2. Using [ProtonUp-Qt](https://github.com/DavidoTek/ProtonUp-Qt) (Recommended):
	1. Download ProtonUp-Qt either using the AppImage or from Flathub or if you are using Arch then it is also available in the AUR. [Download Instructions](https://github.com/DavidoTek/ProtonUp-Qt#protonup-qt)
	2. Open ProtonUp-Qt, if you are using the AppImage then just double clicking on the downloaded file will open ProtonUp-Qt (Make sure the file is executable, Right click on the file and click on "Properties" the check for and option for something like "Mark as executable" or similar, different file manager have different ways to do this so it is difficult for me to tell you exactly)
	3. After opening ProtonUp-Qt a new window will appear and now you can choose the program you want to install Wine on like Steam, Lutris or Bottles. For this guide we click on the drop down menu and select "Lutris".
	4. Then click on "Add version" button, choose a version and click "Install" and now you should have your desired Wine version installed. `NOTE: Make sure you install the non-lol version, the version that ends with -LoL is meant for League of Legends, so it will not work for other games.`
	5. Then restart Lutris if you had it open.
## Which Wine version to choose for Lutris:
I recommend using the wine-ge. It has all the Proton patches and is based on Proton Experimental and the creator of wine-ge and proton-ge is very active and will update it as soon as he can, so you can play newer games with new patches faster than the Lutris builds. I will not recommend using proton-ge with Lutris, you can read more about the [here](https://www.reddit.com/r/linux_gaming/comments/w0vfn1/another_protonge_vs_winege_thread/) and [here](https://github.com/GloriousEggroll/proton-ge-custom#1-running-non-steam-games-with-proton-outside-of-steam-is-not-supported-do-not-ask-for-help-with-this). 	

To install wine-ge in Lutris using ProtonUp-Qt:
1. Open ProtonUp-Qt
2. Select Lutris from the drop down menu
3. Click on "Add version"
4. Select "Wine-GE" under "Compatibility tool"
5. Select your desired version under "Version", If you don't have a desired version the select the latest non-lol version. NOTE: Make sure you install the non-lol version, the version that ends with -LoL is meant for League of Legends, so it will not work for other games.
6. Click "Install", wait for the Installation to finish.
7. Then restart Lutris if you had it open.

`Finally Comes the Actual Process: `
## How to install Windows repacks in Lutris:
1. Open Lutris.
2. Click on the '+'/plus icon on the top left corner.
3. A new window will appear, Click on "Add locally installed game" on the new window.
4. Click on the box beside "Name" and type the name of your game.
5. Click on "Select a runner from the list" then select "Wine (Run windows games)
6. Go to "Game options" tab
7. Make sure you have "Show advanced options" enabled on the bottom left corner of that window.
8. Leave the "Executable" field empty for now.
9. In the "Wine prefix" field you will need to give the path of where you want to create a prefix. A Wine prefix is a folder where a set of files and folder will be kept to create a confined Windows environment. That means inside of your prefix, a fake C:\ drive as a folder will be created and other things required by Wine will be created. Inside of a prefix you will see a folder named "drive_c", this is the folder where folders like "Program Files", "Program Files(x86)", "users", "windows" etc exists.
10. In the "Wine prefix" field type `~/Games/<your-game>`, replace "`<your-game>`" with the name of your game without any "space" or " " and preferable all small letters (eg `~/Games/spider-man`, `~/Games/gtav`, `~/Games/godofwar` or `~/Games/gow`) , this will create the prefix folder in `/home/<yourUsername>/Games/<your-game>`. A single prefix can be created (eg `~/Games/prefix`) and you can use that prefix for all of your games but it is not recommended for beginners but if you know what you are doing you can do that.
11. Now go to the "Runner options" tab.
12. Click on the drop down on the right of "Wine version" and select the latest version of wine-ge you have installed or whichever version you prefer.
13. Now click on "Save".

########################################################################## 

FitGirl Repacks will have a .bat file to check if the repack was downloaded correctly or not, it is recommend by FitGirl to run this before starting installing your game, so to run that:

1. Click on the game your just added.

2. On the botton panel click on the "Up" icon just beside the "Wine Glass" icon or just to the left of the "Platform: Windows" text.

3. Now click on "Run EXE inside Wine prefix".

4. A file picker will appear, select the .bat file inside the FitGirl repack, it should be inside Downloads and the FitGirl folder. Now double click the .bat file.

5. Wait for couple of minute, click "Install" if any installation prompt appears.

6. After a while the "Checking fg-01.bin" windows will appear and wait for it to check all the files and when "All files OK" message appears, close the window. Now you are good to go.

##########################################################################

## Running the installer:

1. Click on the game you just added.
2. On the botton panel click on the "Up" icon just beside the "Wine Glass" icon or just to the left of the "Platform: Windows" text.
3. Now click on "Run EXE inside Wine prefix".
4. A file picker will appear, select the "setup.exe" file your downloaded repack. It should be inside Downloads and the Repack folder you downloaded. Now double click the "setup.exe" file.
5. Wait for couple of minute and let Wine create the prefix folder, click "Install" if any installation prompt appears. (Optionally, You can force it to create the prefix folder before running any exe by just double clicking the game you just added, it will then create the prefix and do its thing, an error will appear after that but just click "ok" and follow from "Running the installer")
6. Now the familiar FitGirl or DODI installer will open.
7. Follow along with the installation until selecting your game destination.
8. In FitGirl repacks by default "Z:\" drive is selected. But installing in "Z:\" drive will not work, it will give an error. The "Z:\" drive is linked to your system's "/" folder and you do not have access to that folder so do not install in "Z:\" drive and also you might have read somewhere to install in "Z:\home\yourUsernam\" and that will work and the installation will complete but Lutris by default sandboxes Wine so that Wine will not have access to any other folders in your system except "Downloads" and the "drive_c" folder inside your prefix, so, an error will occur when trying to launch the game.
9. Click on the "Browse" button or "..." icon besides the destination location in FitGirl's or DODI's installer respectively and just click on "C:\" then click "OK", this will install the game in "C:\Your Game" or in your file manage inside your prefix and inside "drive_c" folder i.e "`~/Games/<your-game>/drive_c/Your Game`"
10. You do not need to create a desktop icon or a start menu entry, so just deselect those options and do not create desktop icon and start menu entry. We will not be launching the game with desktop icons or start menu entry but we will be launching the game from Lutris.
11. Continue the setup until you reach the component selector, their you will need to deselect every option that starts with "Update" for eg: "Update DirectX", disable those options, you do not need to update those.
12. Continue with the installation, and pray you will not get any errors in FitGirl repack :)

## After the installation is completed:


1. Right click on the game, then click on "Configure"
2. Go to "Game Options" tab, the click "Browse" button besides the "Executable".
3. Now go inside your prefix folder, then inside "drive_c", then search for your game folder, inside the game folder should be a .exe file that launches your game, select that exe and click "Ok".
4. Now just double click your game to launch it.

`Also if you are facing unarc.dll or ISDone.dll errors while installing FitGirl's repacks then I would highly recommend trying out DODI's repacks, for me at least DODI's repacks have never failed me`