# How to Install Windows Games on Linux Using Heroic Games Launcher

Hello, fellow Linux gamers! 👋

Before getting into the guide, I want to say thank you to everyone who starred the [original guide on GitHub](https://github.com/elmhadji/instal_repacks_in_Linux).

I hope you like the new guide, and if you need any help or have any suggestions, feel free to ask! ❤️

If you're here, you probably want to know how to install and run a **Windows game on Linux**.

The good news is that, once you understand how Wine/Proton prefixes work, it's actually pretty simple.

## What do you need?

You basically need three things:

1. **A Windows game installer or game files** — either an installer (`setup.exe` from FitGirl, DODI, etc.) or an already-installed game folder.
2. **A Linux distribution** of your choice.
3. **Heroic Games Launcher**, which makes managing Wine/Proton games much easier.

For installing Heroic, you can follow their [official Linux guide](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/wiki/Linux-Quick-Start-Guide).

---

## 1. If you have a game installer

Let's say you have something like:

```text
setup.exe
```

This is the easiest situation to understand because you're essentially going through the same installation process you would on Windows.

### Step 1 — Add the game to Heroic

Open **Heroic Games Launcher** and go to your library. and Click **Add Game**.

### Step 2 — Enter the game information

1. Set the **Title** of your game.

2. *(Optional)* Add artwork from [SteamGridDB](https://www.steamgriddb.com/) by pasting the image URL into the **App Image** field.

3. Set **Platform** to:

   ```text
   Windows
   ```

4. Set the installer as the **Executable**:

   ```text
   /home/<username>/Downloads/setup.exe
   ```

### Step 3 — Configure the Wine prefix

This is one part that's worth understanding.

Linux can't natively run Windows `.exe` files. Heroic uses **Wine** (or Proton) to create a compatibility environment called a **Wine prefix** (a virtual `C:` drive).

My recommended organization is to give every game its own prefix:

For example:

```text
Games/
├── WinePrefixes/
│   ├── HollowKnight/          # Virtual C: drive (registry, Wine/Proton config, saves)
│   ├── Constance/             # Virtual C: drive for Constance
│   └── ForzaHorizon5/         # Virtual C: drive (VKD3D-Proton DX12 shaders & dependencies)
│
└── GameInstalls/              # Actual game data & executables 
    ├── HollowKnight/          # Contains Hollow Knight.exe and game assets
    ├── Constance/             # Contains Constance.exe and game assets
    └── ForzaHorizon5/         # Contains ForzaHorizon5.exe and game assets
```

This isn't the only way to organize things, but keeping separate prefixes makes things much easier to manage later.

If you're new to Wine, **leave the Wine settings at their defaults initially**. 

### Step 4 — Run the installer (and set the game folder)

Click **Run Installer First** to launch the setup wizard. From here, it's the familiar **Next → Next → Install → Finish** 😅—with two crucial details to keep in mind:

> 💡 **FitGirl tip:** If the installer becomes unstable or hangs during installation, try enabling **"Limit installer to 2GB RAM"** in the installer.

When asked where to install the game, change the destination path to an easy-to-find folder, such as:

```text
/home/<username>/GameInstalls/GameName/
```

*(Note: In the installer's file browser, your Linux root directory `/` is listed under the **`Z:\` drive**).*

Keeping your actual game files in a clear location separate from your Wine prefix will save you major headaches later!

### Step 5 — Change the executable

Once the installation finishes, Heroic will still be pointing to: `setup.exe` .

You need to update the **Executable** field in Heroic settings to point to the installed game binary:

```text
/home/<username>/GameInstalls/GameName/Game.exe
```

Save the configuration.

Now click **Play**.


---


## 2. If you already have the game installed

If you already have a pre-installed folder:


```text
GameName/
├── Game.exe
├── data/
├── engine/
└── ...
```

1. Go to **Heroic → Add Game**.
2. Set **Platform** to `Windows`.
3. Set **Executable** directly to the game binary:
   ```text
   /home/<username>/GameInstalls/GameName/Game.exe
   ```
4. Set your preferred Wine/Proton version and prefix location.
5. Save and click **Play**.

*Note: The first launch might take a few extra seconds because Heroic is generating the Wine prefix in the background.*

---

## A small but important detail about Wine prefixes

A **Wine prefix** is an isolated Windows environment created by Wine. It contains standard Windows folders:

```text
WinePrefixes/GameName/
└── pfx/
    └── drive_c/
        ├── Program Files/
        ├── Program Files (x86)/
        ├── users/
        └── windows/
```

Keeping your **Wine prefix** separate from your **Game files** (`/home/<username>/GameInstalls/GameName/`) makes troubleshooting, backing up saves, and modding significantly easier.

---

## Quick Summary Workflow

### Installer (`setup.exe`) Workflow
```text
Add Game → Select Windows → Select setup.exe → Run Installer 
  → Set game install directory (/home/<username>/GameInstalls/GameName/)
  → Finish setup → Change Executable to Game.exe → Play
```

### Pre-Installed Folder Workflow
```text
Add Game → Select Windows → Select Game.exe → Configure Wine/Proton → Play
```

Once you understand those two workflows, installing Windows games on Linux becomes much less intimidating.

If a game doesn't launch right away, **don't assume Linux can't run it**. Try changing the Wine/Proton version in Heroic, installing missing dependencies via Winetricks, or checking ProtonDB for launch flags!
