# iTunes Apple Script: Convert Cyrillic Instant tool 

Cyrillic Convertor for iTunes Исправлялка для песен в Русские буквы (кириллица) когда видешь каракули))
Исправляет следующие поля: "Name", "Artist", "Album Artist", "Album"

Script:
	Convert Cyrillics for your music files the following fields only: "Name", "Artist", "Album Artist", "Album". Based on original script by Andrei Popov
(https://code.google.com/p/as-convert-russian/source/browse/trunk/Convert+Russian.applescript?r=12)
Version:
	0.3 - with added check for characters which are already good cyrillic - to avoid resulting in "??????" cause that was annoying
Author:
	Ruslan Schelkunov https://github.com/ruslanss

The issue:
	ID3 tags that are embedded in MP3 files generated on Windows or (shudder) DOS machines use extended ASCII to store Cyrillics.  When you import such files into iTunes, it assumes that they're all in MacRoman coding page** and happily garbles them up.

The search to solve it:
	One way to do that is to convert tags *before* importing them into iTunes.  This might work, but I have not tried it, don't know.
	Another way was to try and fix them once they're in using a `do shell command' call from AppleScript.  No luck there, although iconv -f cp866 -t utf8 *almost* does the right thing.  Almost, but not quite.

Solution:
	I had to manually recode conversion table, based on MacRoman ASCII page (http://www.iro.umontreal.ca/~felipe/IFT1010-Hiver2005/Complements/ascii.html) viewed as if it were Cyrillic (Mac) page in Camino, then assigning proper UNICODE values to each code point.

Credits:
	Thanks to StefanK at MacScripter BBS  for helping me sort out a few AppleScript issues.
	Thanks to Sergii Denega for providing a number of further fixes, most importantly to make script work on both PPC and Intel and fixing the issue with multiple tracks to be convereted.
	Thanks to Teodor Zlatanov for providing changes that allow choosing what fields/tags should be converted.

----
** Some say this would not be the case if International pannel lists Russian as first language -- I have not tested that
