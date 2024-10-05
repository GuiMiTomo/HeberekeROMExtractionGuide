# WARNING!

 This guide is now outdated. Check out Infinest's [Hebereke Enjoy Edition Extractor](https://github.com/Infinest/Hebereke_Enjoy_Edition_Extractor/) and its corresponding [https://steamcommunity.com/sharedfiles/filedetails/?id=3340850622](Steam guide) for a more updated ROM extraction method.

 --X--

This is a ROM Extraction Guide for [Hebereke Enjoy Edition](https://store.steampowered.com/app/2869000/HEBEREKE_Enjoy_Edition/) on Steam.

### What you'll need?
- Hebereke Enjoy Edition (obviously)
- Task Manager
- A hex editor (like HxD)
- [This patch file](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/releases/tag/hebereke-patch)
- A ROM patcher (like [this one](https://www.marcrobledo.com/RomPatcher.js/))
- A NES emulator

### Note
This guide was made on version **1.01.29**.

### Getting the ROM
First start Hebereke Enjoy Edition.

Make sure the game is running.

![image](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/assets/76497419/88dae2bf-f7f3-4bc3-b7cb-5cbe639445b1)

While Hebereke is running, open Task Manager, and head over FCHEBEREKE.exe

Right click on FCHEBEREKE.exe and select "Create capture file*" to get a memory dump.

*Translated from portuguese, my bad.

![image](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/assets/76497419/a4f47ea4-8441-4cd2-8d37-8988256366a2)

Wait for it, and once the memory is dumped, select "Open file location".

![image](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/assets/76497419/67f841df-a226-4a8f-afb6-243075d634ad)

Now you'll get the FCHEBEREKE.DMP file. Move it to anywhere else into your computer.

![image](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/assets/76497419/de993474-16e4-4c0e-a71f-8351ef25d665)

Now open FCHEBEREKE.DMP into the Hex Editor of your choice. Now, search for for the following hex data:
```
00 02 02 02 02 02 00 00 00 00 00 8F 80 00 80 00
```
This is the beginning of the first half of the ROM.

Then delete everything before the data you just searched. This will reduce the size of the file.

After that, search the following hex data.
```
FF 00 F5 56 0A 08 00 00 00 FF FF FF FF BF BF 9E
```
This starts the other half of the ROM.

Delete the data between 0x00020000 (the first half ends at 0x0001FFFF) and the one before the offset you just searched.

After that, delete the data after 0x0003FFFF.

Add the following iNES header at the beginning of the file:
```
4E 45 53 1A 08 10 50 48 00 00 00 00 00 00 00 01
```

Save the file and you'll get a ROM file. If you see the title screen in the emulator, that means it worked.

![image](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/assets/76497419/07e7da9a-0deb-4b4f-a8b8-7fc773a9a1ba)

If you see a black screen after starting the game, that's normal.

![image](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/assets/76497419/99519657-4a84-41e6-ae8e-bf559cfa2621)

### Making the ROM Playable

This is where the patch enters in action.

Open the ROM Patcher and insert the patch file I provided.

![image](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/assets/76497419/3eaa700b-813a-40b3-b869-f485b995b1f9)

Apply it and run the new ROM on the Emulator. Start a new game.

![image](https://github.com/GuiMiTomo/HeberekeROMExtactionGuide/assets/76497419/dcdc2e97-6f27-475e-af3d-a0e457b6b220)

The game now should be playable. You can now play it on an emulator, your NES mini or something.

### Piracy

Don't share the ROM with anyone or anywhere else on the Internet, just because this is **your own** copy. Piracy is a serious crime.

### Problems with the guide?

Please open an issue.
