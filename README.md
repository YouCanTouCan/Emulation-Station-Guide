# Emulation-Station-Guide
A description for how to get Emulation Station working with Steam, Retroarch, Epic Games, GOG, and other executable games when on either Aurora (a version of Fedora) or Windows.

The explanation for Aurora is likely extremely applicable to other distributions, Aurora is just what I personally use and can verify that as of writing this these steps work on. I do not use Windows myself, so that section I am less sure about.

## 1. Initial Setup
First, lets actually download Emulation Station, and do some initial setup

1. You can simply download it [here](https://es-de.org/#Download) - If you are on Linux, select the first AppImage (except if you are on the Steam Deck, then go for the second) and if you are on Windows go for the Windows Installer download, then run through the installation process that the installer guides you through.
2. Open Emulation Station
3. Click Esc, then select UI Settings, then Theme Downloader
4. Select what theme you want! For this guide, I will assume you are using "Iconic", that is my personal favorite.
5. Close Emulation Station
6. Download es_Settings.xml from this repository
7. Go to C:\Program Files\ES-DE\settings (Windows) or Home/ES-DE/settings (Linux) and replace the es_Settings.xml there with the one you downloaded from this repository
8. Open the new es_Settings.xml in some text editor, it doesn't matter what program.
9. On line 135, change `<string name="ROMDirectory" value="/home/[REPLACE-THIS]/Games" />` to `<string name="ROMDirectory" value="[ROM Directory]" />` where [ROM Directory] is a folder you select somewhere on your computer. The specific location does not matter, but make sure you know what you set it as and that, ideally, the folder is empty. I used `home/Games`. 
10. Save and close es_Settings.xml

## 2. Organizing your File System
To make our lives easier further down the line, it is best to ensure that our games files are well-organized. 

1. Remember the ROM-Directory folder you selected/made in step 1.9? I hope you do. Go there in your file explorer.
2. Create a separate folder for each console you want a section on within Emulation Station. 
   1. The following consoles are those with pre-made art and info for them. If you want to do another console, you can, it will just take some more work down the line, so I recommend following these names if you can. If you are, for example, emulating a DS, name the folder "nds" - keep it exactly the same as the names listed here: '3do', '3ds', 'amiga', 'amigacd32', 'amstradcpc', 'apple2', 'arcade', 'arcadia', 'astrocde', 'atari800', 'atari2600', 'atari5200', 'atari7800', 'atarijaguar','atarijaguarcd', 'atarilynx', 'atarist','atomiswave', 'c16', 'c64', 'c128', 'channelf','coco', 'coleco', 'daphne', 'dragon32','dreamcast', 'easyrpg', 'fba', 'fds','gameandwatch', 'gamegear', 'gb', 'gba', 'gbc','gc', 'genesis', 'intellivision', 'mame-advmame','mame-libretro', 'mame-mame4all', 'mastersystem','megacd', 'megadrive', 'moto', 'msx', 'msx2','n64', 'naomi', 'nds', 'neogeo', 'neogeocd','nes', 'ngp', 'ngpc', 'openbor', 'oric', 'pc','pc88', 'pc98', 'pcfx', 'pcengine', 'pcenginecd','pico8', 'pokemini', 'ports', 'ps2', 'psp','psx', 'saturn', 'scummvm', 'sega32x', 'segacd','sg-1000', 'snes', 'steam', 'switch', 'ti99','trs-80', 'vectrex', 'vic20', 'videopac','virtualboy', 'wii', 'wiiu', 'wonderswan','wonderswancolor', 'x68000', 'x1', 'zmachine','zx81', 'zxspectrum'
3. Inside each console, you want to place the file that is used to launch the game. This may be easier or harder depending on the game we are talking about. For something like a DS-era Pokemon game, for example, all you need to do is place the .nds file inside the nds folder and you're done. 
