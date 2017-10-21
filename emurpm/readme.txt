written by Dark Byte @ smashboards.com
provided by Punkline @ smashboards.com
https://smashboards.com/threads/using-cheat-engine-with-dolphin.442909/
This thread was written for GALE01 (Super Smash Bros. Melee) but I have adapted it for use with Animal Crossing.
Notes on changes will be written underneath excerpts.

>Download Cheat Engine. I recommend the portable version, which you don't even need to install. 
>It’s also got a github if you’d like to noodle with the source.
>Open it up and click on the flashing icon for a prompt to select your running Dolphin process.
[linked are the cheat engine websites and github page.]
[CE website: http://www.cheatengine.org/downloads.php]
[CE portable: http://www.cheatengine.org/download/CheatEngine66_NoSetup.rar]
[CE gitbuh: https://github.com/cheat-engine/cheat-engine]
>Enable MEM_MAPPED regions in your scan settings so that the program can see emulated RAM.
>https://smashboards.com/proxy.php?image=http%3A%2F%2Fi.imgur.com%2FGcVom13.png&hash=e4db834a0e4d70b45fe5ab640dd88d3e
[the settings are in Cheat Engine settings > Scan Settings, under "Scan the following memory region types"]

>[...] extract its contents into the autorun folder of your Cheat Engine directory.
>This adds an indispensable menu item called “Emulator Memory” to the main menu bar, 
>which allows you to adjust the base memory address used by Cheat Engine when looking at a process. 
>I’ve only recently learned about this, and using CE without it is a sort of hell.
>
>In every case I’ve seen of 64-bit Dolphin 4.0+ the base address for logical cached RAM appears 
>to be represented by 0x7FFF0000 in Cheat Engine. There are other possible ranges that can be used, 
>but I’ve found some of them to be inconsistent and haven’t had any trouble with this location across versions--
>so I assume it is the start of the logical cached region.
>Try these settings if you’re using Dolphin 4.0+
>https://smashboards.com/proxy.php?image=http%3A%2F%2Fi.imgur.com%2FxffqHs0.png&hash=18e867144e1658c9f6f4c53cef6f3071
[TRANSCRIPTION]
(Emulator memory)
Fill in the address or pointer to the emulated memory
	7FFF0000 -80000000
Size of memory (in KB, can use lua commands)
	0x81800000
<(Re)Set address>

>If you’re using an older version of Dolphin, the address we’re looking for doesn’t even appear to be static 
>and must be referenced with a pointer. You might have luck with settings similar to what I use for this old 
>fastlog build, which I often rely on for memory check breakpoints and live browsing of the disassembler. 
>If this doesn’t work, you’ll have to hunt for the appropriate pointer by studying GALE01 locations via scan (or update Dolphin.)
["fastlog build" is highlighted and links to another page, pasted below.]
https://smashboards.com/threads/dolphin-debugfast-4-0-emulator-memory-breakpoints-download-links-32-64-bit.354071/#post-17022789
>https://smashboards.com/proxy.php?image=http%3A%2F%2Fi.imgur.com%2FepydZpX.png&hash=e4ec7cea59c07cc11cd679d25a2ef778
[TRANSCRIPTION]
(Emulator memory)
Fill in the address or pointer to the emulated memory
	[DolphinDF.exe+4D64BF8] -80000000
Size of memory (in KB, can use lua commands)
	0x81800000
<(Re)Set address>

[attempting this threw an error, saying cheat engine couldn't parse what the pointer meant.]
[my solution was simply using "[Dolphin.exe]+7FFF0000" in place. the memory size remained the same.]

