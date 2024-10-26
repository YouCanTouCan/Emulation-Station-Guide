# ES-DE Guide
A description for how to get ES-DE working with Retroarch, Steam, Epic Games, GOG, Amazon Prime Games, Prism Launcher (Minecraft), Lutris, Bottles, and any other games when on either Aurora (a version of Fedora) or Windows.

The explanation for Aurora is likely extremely applicable to other distributions, Aurora is just what I personally use and can verify that as of writing this these steps work on. I do not use Windows myself, so that section I am less sure about.

This was made by me solely for my brother who saw my setup and thought it was cool. If you are someone else, feel free to use it, but no promises that I will keep editing this in the future to make sure it keeps working or includes more use-cases.

## 1. Initial Setup
First, lets actually download ES-DE, and do some initial setup

1. You can simply download it [here](https://es-de.org/#Download) - If you are on Linux, select the first AppImage (except if you are on the Steam Deck, then go for the second) and if you are on Windows go for the Windows Installer download, then run through the installation process that the installer guides you through.
2. Open ES-DE
3. Click Esc, then select UI Settings, then Theme Downloader
4. Select what theme you want! For this guide, I will assume you are using "Iconic", that is my personal favorite.
5. Close ES-DE
6. Download es_Settings.xml from this repository
7. Go to C:\Program Files\ES-DE\settings (Windows) or Home/ES-DE/settings (Linux) and replace the es_Settings.xml there with the one you downloaded from this repository
8. Open the new es_Settings.xml in some text editor, it doesn't matter what program.
9. On line 135, change `<string name="ROMDirectory" value="/home/[REPLACE-THIS]/Games" />` to `<string name="ROMDirectory" value="[ROM Directory]" />` where [ROM Directory] is a folder you select somewhere on your computer. The specific location does not matter, but make sure you know what you set it as and that, ideally, the folder is empty. I used `home/Games`. 
10. Save and close es_Settings.xml

## 2. [OPTIONAL] Signing up for a Screenscraper Account
ES-DE has two websites it can scrape, which is how it gets all the fun artwork and stuff. Screenscraper, which is superior for older games, and TheGamesDB, which is superior for newer PC games. Both work without an account, but Screenscraper is slower when you aren't signed in. Thus, if you have a decent number of ROMs, it may make sense to take the few minutes to make an account.

1. Go to [this website.](https://screenscraper.fr/) Yes, I know it looks horrendous, but it has the goods we need, and once we are done here we won't ever need to lay eyes on it again.
2. At the top right, you'll see a yellow "Register" button. Click it.
3. Scroll down until you see a spot to put in a Username, Password, and Email. Fill it out.
4. Click the yellow "Send" button.
5. You may need to confirm your email, I don't remember. Check your email and do so if prompted.
6. Open ES-DE
7. Click Esc
8. Select Scraper
9. Select Account Settings
10. Put in your username and password, and make sure the option to use this account for screenscraper is turned on

## 3. Organizing Your File System
To make our lives easier further down the line, it is best to ensure that our games files are well-organized. 

1. Remember the ROM-Directory folder you selected/made in step 1.9? I hope you do. Go there in your file explorer.
2. Create a separate folder for each console you want a section on within ES-DE. 
   a. The following consoles are those with pre-made art and info for them. If you want to do another console, you can, it will just take some more work down the line, so I recommend following these names if you can. If you are, for example, emulating a DS, name the folder "nds" - keep it exactly the same as the names listed here: adam, arcade, atari5200, atari7800, atari800, atarixe, coco, colecovision, cps, dos, dreamcast, famicom, gameandwatch, gamegear, gb, gba, gbc, intellivision, lcdgames, mame, mastersystem, megacd, megacdjp, megadrivejp, model1, n3ds, n64, nds, neogeocd, neogeocdjp, nes, ngp, now-playing, pcengine, pico8, ps2, psvita, saturn, scummvm, ega32x, sega32xna, segacd, sfc, sgb, snes, snesna, steam, sufami, tg-cd, tg16, trs-80, wiiu, wonderswan, wonderswancolor, xbox, xbox360

## 4. Entering Your Games
Time to bring our games in!

### Emulated Games:
This part of the guide is for any game that you run through an emulator such as Retroarch.

1. Simply move the ROM file over to the relevant console folder inside your ROM Directory. For example, if you are emulating Pokemon White, go to the ROM Directory from steps 1.9 and 3.1, then go inside your "nds" folder, and put the Pokemon-White.nds file (or whatever its called for you) in there
2. Open ES-DE
3. Press Esc, then select "Scraper"
4. Under "Scrape from" select Screenscraper if it isn't already selected
5. Under "Scrape These Systems" select each of the systems you put ROM files into
6. Click Start and wait till it's finished

### Steam Games, Epic Games, GOG, & Amazon Prime Games:
Any game you installed through one of these four game launchers. It must be downloaded on your computer to appear in ES-DE, games you for example own on steam but don't have installed won't work. For linux users, it takes more effort if Steam or Heroic Games Launcher (Epic, Gog, and Prime) is installed through flatpak - check that section seperately.

1. [🪟 WINDOWS ONLY 🪟] Go to C:\ProgramData\Microsoft\Windows\Start Menu\Programs and find all files that are the name of a game then .url - for example Undertale.url. Select all these files and copy them. Go to your ROM Directory from steps 1.9 and 3.1, then go inside your "steam" or "pc" or whatever folder (whichever you prefer), and paste the files.
   a. If your C:\ProgramData\Microsoft\Windows\Start Menu\Programs is empty or doesn't have the games, maybe try checking AppData\Roaming\Microsoft\Windows\Start Menu\Programs\ instead. They should be in one of the two.
2. [🐧 LINUX ONLY 🐧] Find your .desktop files for each steam game you have. Select all these files and copy them. Go to your ROM Directory from steps 1.9 and 3.1, then go inside your "steam" or "pc" folder (whichever you prefer), and paste the files.
3. Open ES-DE
4. Press Esc, then select "Scraper"
5. Under "Scrape from" select TheGamesDB if it isn't already selected
6. Under "Scrape These Systems" select each of the systems you put the .url or .desktop into
7. Click Start and wait till it's finished

### Steam Games, Epic Games, GOG, & Amazon Prime Games [FLATPAK]:
If you installed Steam or Heroic Games Launcher (a frontend for Epic, Gog, and Prime) through flatpak, it takes a little more work to get them working through ES-DE unfortunately.

1. Remember the ROM-Directory folder you selected/made in step 1.9? I hope you do. Go there in your file explorer.
2. Go into your folder for these games - perhaps "steam" or "pc" or "epic" or so on.
3. Make a file with the name of a game installed through this method, then .sh. So, for example. "Undertale.sh".
4. Open the file
   1. If it is a steam game, paste the following into the file:
      `#!/bin/bash
      flatpak run com.valvesoftware.Steam :steam steam://rungameid/200260`

### Minecraft Instances:
Kinda niche, but this is the section for if you want to run a specific instance of Minecraft from within ES-DE. This can be a specific set of mods, resource packs, shaderpacks, settings, or so on. You can even launch into a Minecraft server directly from ES-DE following this guide. IT IS ASSUMED YOU USE PRISM LAUNCHER AND HAVE IT SETUP ALREADY. Get it from [here](https://prismlauncher.org/download/) if not.

### Other Executable Games:
Any game that isn't covered by another guide here and that you just run directly from an executable file on your computer. 

### Lutris Games:
Lutris is a way to run games on Linux, if you are on Windows this section is useless to you. 

### Windows Games through Bottles:
Bottles is a way to run Windows apps on Linux, if you are on Windows this section is useless to you. 
