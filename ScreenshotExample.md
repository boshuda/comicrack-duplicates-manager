See it in action...

![http://i750.photobucket.com/albums/xx149/perezmu/dm.jpg](http://i750.photobucket.com/albums/xx149/perezmu/dm.jpg)

# Example dmrules.dat #

```

# this example removes fileless and 
# selects the noads files with largest filesize

# we can set options

@ MOVEFILES       true
@ REMOVEFROMLIB   true

# and now the rules

pagecount	remove	fileless
pagecount	keep	noads
filesize	keep	largest	

```

# Example logfile.log #

```

COMICRACK DUPLICATES MANAGER V 0.1

Parsing 10 ecomics


============= Beginning rules parsing ==================================

Successfully read the following rules: 

	  pagecount    keep    noads
	  filesize	keep	largest


============= End of rules parsing ======================================



============= Begining dupes identification ==================================

Parsing 10 ecomics
Found 1 different series
Found 1 different series with more than one issue
Found 1 different series with dupes
Found 2 groups of dupes, with a total of 10 ecomics.

============= End of dupes identification=====================================



============= Beginning dupes processing =====================================


= PROCESSING GROUP_____
= brightestday #17

_________________KEEP_PAGECOUNT_NOADS______________
keeping... Brightest Day 17 (2011) (two covers) (Minutemen-DTs).cbz (pages 22)
removing... Brightest Day 017 (2011) (noads) (2 covers) (Archangel & FP-CPS).cbz (pages 28)
removing... Brightest Day 017 (c2c) (2011) (The Last Kryptonian-DCP).cbz (pages 32)
removing... Brightest Day 017 (2011) (c2c) (2 covers) (Archangel & FP-CPS).cbz (pages 33)
removing... Brightest Day 17(c2c)(2 covers)(DC)(2011)(YZ1).cbz (pages 33)
---MOVED... Brightest Day 017 (2011) (noads) (2 covers) (Archangel & FP-CPS).cbz
---REMOVED FROM LIBRARY... Brightest Day 017 (2011) (noads) (2 covers) (Archangel & FP-CPS).cbz
---MOVED... Brightest Day 017 (c2c) (2011) (The Last Kryptonian-DCP).cbz
---REMOVED FROM LIBRARY... Brightest Day 017 (c2c) (2011) (The Last Kryptonian-DCP).cbz
---MOVED... Brightest Day 017 (2011) (c2c) (2 covers) (Archangel & FP-CPS).cbz
---REMOVED FROM LIBRARY... Brightest Day 017 (2011) (c2c) (2 covers) (Archangel & FP-CPS).cbz
---MOVED... Brightest Day 17(c2c)(2 covers)(DC)(2011)(YZ1).cbz
---REMOVED FROM LIBRARY... Brightest Day 17(c2c)(2 covers)(DC)(2011)(YZ1).cbz

= PROCESSING GROUP_____
= brightestday #18

_________________KEEP_PAGECOUNT_NOADS______________
keeping... Brightest Day 18 (2011) (two covers) (Minutemen-DTs).cbz (pages 25)
keeping... Brightest Day 018 (2011) (noads) (2 covers) (AngelicLegion-CPS).cbz (pages 26)
removing... Brightest Day 018 (2011) (c2c) (The Last Kryptonian-DCP).cbz (pages 35)
removing... Brightest Day 018 (2011) (c2c) (2 covers) (AngelicLegion-CPS).cbz (pages 36)
removing... Brightest Day 18(c2c)(2 covers)(DC)(2011)(YZ1).cbz (pages 36)
---MOVED... Brightest Day 018 (2011) (c2c) (The Last Kryptonian-DCP).cbz
---REMOVED FROM LIBRARY... Brightest Day 018 (2011) (c2c) (The Last Kryptonian-DCP).cbz
---MOVED... Brightest Day 018 (2011) (c2c) (2 covers) (AngelicLegion-CPS).cbz
---REMOVED FROM LIBRARY... Brightest Day 018 (2011) (c2c) (2 covers) (AngelicLegion-CPS).cbz
---MOVED... Brightest Day 18(c2c)(2 covers)(DC)(2011)(YZ1).cbz
---REMOVED FROM LIBRARY... Brightest Day 18(c2c)(2 covers)(DC)(2011)(YZ1).cbz
_________________KEEP_FILESIZE_LARGEST______________
removing... Brightest Day 018 (2011) (noads) (2 covers) (AngelicLegion-CPS).cbz(size 11.5653858185)
keeping... Brightest Day 18 (2011) (two covers) (Minutemen-DTs).cbz(size 22.3294181824)
---MOVED... Brightest Day 018 (2011) (noads) (2 covers) (AngelicLegion-CPS).cbz
---REMOVED FROM LIBRARY... Brightest Day 018 (2011) (noads) (2 covers) (AngelicLegion-CPS).cbz



\ ########################################################### n

Scritp execution completed correctly on: 10 books.
2 duplicated groups processed.
0 duplicated groups remain..
2 comics remain
```