
---


---


# Tips #

Some useful tips for using the script:

  * Run a traditional dupes program to remove identical files first!

  * It was designed with 0-days in mind, but should be useful in many more cases. Keeping the original filename (or copying it to the notes field) is useful as will be seen in the examples below

  * Some variables can be edited by the user in the `dmrules.dat` file, (while the the directory where the dupes are moved to must be changed in the `constant.py` file).

  * No matter what rules you set, the script will NEVER delete/move all the files in a given duplicates group. If a rule would delete all the comics, then none will be removed!!!!

  * Spacing in the rules file is free, you can use it at will, including tabs, as long as you keep one rule for each line, and only one rule per line.

  * Note that _words_ in the rules are sentences that will be searched in the same order as entered!

  * **Fileless** files are only touched by the rules that explicitly address them (this is, if you remove the comics with lowest number of pages, this will not include fileless -pagecount = 0-)


---


---


# Examples #


---


## Keep the one with the larger filesize ##

This is straightforward. Just remember this rule and similar ones (with largest or smallest) always keep only one file!!!!!:

```
  filesize   keep   largest
```


---


## Keep always "fixed" files ##

Sometimes scans include "(fixed)" in their name, meaning they are bound to replace previous broken scans... to get always these, use this rule:

```
   filename   keep   fixed
```

Note that this might also work:

```
   text    keep    fixed
```


---


## Prefer always files from a given directory ##

Sometimes you'd prefer to keep the files from a given directory..., for instance, let's say the directory where you store a given Chronology easy as pie:

```
   filepath   keep   chronology
```


---


## Substitute fileless by new ecomics ##

If you want to substitute your fileless comics with the new scans added to your library, you should select them all and run the script with the following **dmrules.dat** file:

```
  pagecount   remove   fileless
```


---


## Keep only the comics from your prefered scanner(s) ##

Let's say you like the scans of Bchry best, then GreenGiant and finally those from other DCP scanners, you could select the proper ones by using these rules (remember, these are all case insensitive!):

```
  text  keep   Bchry
  text  keep   GreenGiant
  text  keep   DCP
```

This is how this works: the first line searches for Bhcry's scans and if it finds any, removes the rest of the scans for that book... If it doesn't find any, no ecomic is removed. So, for those dupes in which there was a Bchry scan, you are all set... for the rest of the dupes groups, the script proceeds with the next rule... doing exactly the same for GreenGiant's scans... Finally for those groups without tagged Bchry or GreenGiant scans, those tagged with "DCP" are preserved and the rest removed (as always, if in a group none of the rules finds a match, then all comics are preserved).



---


## Keep the **noads** comic with the largest number of pages ##

If all comics have in their name, or tags, or notes the **noads** or **c2c**
it is pretty straightforward. You just go:

```
   text      keep    noads
   pagecount count   largest
```

But if not all comics are properly described, you can let the script try and guess which are **noads** and which **c2c**, then you can use these rules instead:

```
   pagecount  keep   noads
   pagecount  keep   largest
```