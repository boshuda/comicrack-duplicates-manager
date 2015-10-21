## Introduction ##

Removing duplicate ecomics can be a very time consuming process when done by "hand", both, in Windows Explorer or within Comicrack. This script aims to help automate that process **following a simple "rules-based" approach**.

Consider the following complex situation posted by one of the fellow members of the Comicrack forum:

> _e.g. Suppose we have 3 different scans of a book.. like Comic 1 (Scanner X), Comic 1 (Scanner Y), and Comic 1 (Scanner Z). Now, I always prefer Scanner X more than Y more than Z. So, I would like to keep the Scanner X book here. A simple scenario._

> Next step is bit complicated. Here we have Comic 1 (Scanner X), and Comic 1 (two covers) (Scanner Y). Obviously, I prefer comics with maximum number of covers. But, Scanner X is the preferred one. So, what do we do here?

> The last and the most difficult one. Here we again have 3 scans.. Comic 1 (c2c) (Scanner X), Comic 1 (two covers) (noads) (Scanner Y), and Comic 1 (two covers) (c2c) (Scanner Z). The preference is c2c. Now, add this to the previous 2 preferences (X>Y>Z and number of covers) ,and we have a headache at our hands.


Dealing with this is not easy... but I think the rules approach is the way to go.


The script works as follows:

  * user defines the rules to process duplicate files (see below)

  * script tries to identify duplicated files, grouping them

  * for each group, the script applies the user defined rules until it reaches the end of the rules list, or only one comic remains in the group

  * if any rule would cause the group to get empty (delete all comics) the rule will be skipped

  * files are moved to a dump directory and/or removed from library (see UserConfiguration)

So far the script is at a very early stage with no fancy interface, so it requires some file editing to configure and set the rules... improvements will come, I hope.

F.Y.I, the following rules would accomplish what our fellow forum user requires:

```
    text   keep   c2c
    covers keep   all
    text   keep   ScannerX
    text   keep   ScannerY
    text   keep   ScannerZ
 
```


---


## Installation ##

Download from the downloads section. The script is packed as a `.crplugin` file, so you can install it from Comicrack or double-click in explorer. In either case, the installation will create a new directory in the scripts directory.


---


## Editing Rules File ##

Now you need to edit the file `dmrules.dat` that is located in this directory, to include the rules you want to use. See RulesFileSyntax for details. I am sorry you need to do this manually... sometime there will be a fancy windows form for this...


---


## User configuration ##

There are a series of parameters you can configure. See UserConfiguration for that. In any case, be aware that:


**NOTE FOR VERSION 0.5** : Since I do not want to mess with your files & library before we are sure this thing works right,
|**the script out of the box will not move or remove any comic, just log what it would do in the logfile. To enable the actual processing of files you need to edit the file `constants.py` and set to true the variables `MOVEFILES` and `REMOVEFROMLIB` or set the values in the `dmrules.dat` (preferred).** See the [Configuration Options](http://code.google.com/p/comicrack-duplicates-manager/wiki/UserConfiguration?ts=1297328384&updated=UserConfiguration) Wiki page for details.|
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|


---


## Usage ##

Select your comics in Comicrack, launch the script, and pray! The `logfile.log` file in the dump directory will tell you what happened!

See TipsAndTricks for further help! And you can check also the threat in ComicRack for further discussion Discussion is provided in the ([comicrack support forum](http://comicrack.cyolito.com/forum/13-scripts/12076-duplicates-mnager#12076)).