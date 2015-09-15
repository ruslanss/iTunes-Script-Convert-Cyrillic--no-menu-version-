# iTunes Apple Script: Convert Cyrillic Instant tool 

Cyrillic Convertor for iTunes

Исправлялка для песен в Русские буквы (кириллица); когда видешь каракули
Исправляет следующие поля: "Name", "Artist", "Album Artist", "Album".
aka Cyrillic Unicode rewriter,  ID3 tag convertor.

**Проблема:**
Ваша коллекция MP3 была создана на Windows или по какой–либо иной причине ID3 тэги были записаны в кодировке cp-1251 (a.k.a. win-1251 или ms-cyrillic). Вы наконец купили Мак и только что перетащили все это "собрание сочинений" в iTunes. О, ужас — вместо нормальных названий исполнителей и песен, вы видите кучу непонятных символов.

**Пример:** 
`Ïåñî÷íûå Ëﬂäè - Îñòàâü-Îñòûíü (Feat. Ñêàòî)` с помощью этой утилиты превратиться в 
 `Песочные Люди - Оставь-Остынь (Feat. Скато)`

**Script:**
	Convert Cyrillics for your music files the following fields only: "Name", "Artist", "Album Artist", "Album". 


**The issue:**
	ID3 tags that are embedded in MP3 files generated on Windows or (shudder) DOS machines use extended ASCII to store Cyrillics.  When you import such files into iTunes, it assumes that they're all in MacRoman coding page** and happily garbles them up.
	
	
		
**Version history:**

* 0.4 - with special handler for И > Й as it wasn't working before
* 0.3 - with added check for characters which are already good cyrillic - to avoid resulting in "??????" because that was annoying

**Author:**
	Ruslans Scelkunovs https://github.com/ruslanss

**Credits:**
	Based on original script by Andrei Popov
(https://code.google.com/p/as-convert-russian/source/browse/trunk/Convert+Russian.applescript?r=12)