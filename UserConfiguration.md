
---


---


# Introduction #

**NOTE FOR VERSION 0.5** : Since I do not want to mess with your files & library before we are sure this thing works right,
|**the script out of the box will not move or remove any comic, just log what it would do in the logfile. To enable the actual processing of files you need to edit the file `constants.py` and set to true the variables `MOVEFILES` and `REMOVEFROMLIB`, or set these values using the _`dmrules.dat`_ file (recommended).**|
|:|


---


# Where? #

Default values for options are defined in the file `constants.py` in the script directory. **If the values are changed in the `constant.py` file, then ComicRack has to be re-started for the new values to take effect**.

|**As of version 0.5, the options** (except the `DUPESDIRECTORY`) **can be** 'dinamically' **set** (meaning there is no need to restart ComicRack) **using the `dmrules.dat` file.**|
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

To set an option in the `dmrules.dat` file the following syntax must be used:
```
@ OPTION VALUE
```
For example:
```
@  MOVEFILES     TRUE
@  COVERPAGES    7
```


---


# Options #

## Boolean Options ##

These rules only accept the **True** or **False** values:

  * **`MOVEFILES`** : If set to `False`, no file will be moved, just a logging of what would be done is recorded in the logfile (stored in `DUPESDIRECTORY` as `logfile.log`). If set to `True` comic files will be actually moved to the dump directory (`DUPESDIRECTORY`).

  * **`REMOVEFROMLIB`** : If set to `False`, no ecomic will be removed from the library, just a logging of what would be done is recorded in the logfile (stored in `DUPESDIRECTORY` as `logfile.log`). If set to `True` ecomic will be actually removed from the library.

  * **`VERBOSE`** : This defines the level of debug info dumped to the logfile. It only should be set to True to notify bugs and send the logfile to the project owner for debugging.

## Integer Options ##

  * **`C2C_NOADS_GAP`** : The script tries to separate 'noads' from 'c2c' based on the number of pages of the dupes. It makes two groups so that the difference in pages from one group to the other is at least this number. Defaults to '5'. You can change it if you notice your groups are not being correctly identified.

  * **`COVERPAGES`** : The "`pagecount keep noads`" rules tries to separate noads from c2c ecomics by looking at the page info and looking for gaps as given by `C2C_NOADS_GAP`. This approach has the caveat that if you have comics with 2 pages (tipically covers only) and 24 (typical noads), this would keep the covers only and remove the real noad. For this, the `COVERPAGES` option can be set to an integer number, so that comics with less pages than this value will be skipped by the rule. This option defaults to 4. In the example above, the rule would skip (keep) the cover only ecomic, and keep the actual 24 pagers (if a 32 pager was found, it would be correctly removed).

  * **`SIZEMARGIN`** : _placeholder_ still not implemented

## Other Options ##

As of version 0.5, this option can only be set in the **constants.py** file, not through the **dmrules.dat** file.

  * **`DUPESDIRECTORY`** : Path to the dump directory where all discarded dupes will be moved,  _and the logfile (`logfile.log`) is stored_. Defaults to `C:\__dupes__`. To change to other path, use this syntax: For example `D:\MyComics\Discarded` you should set `directoryPath.Combine("D:\\","MyComics","Discarded")`