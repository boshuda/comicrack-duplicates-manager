
---


---


# Introduction #

The script requires for proper function a text file (no fancy encoding) in the script directory, named **dmrules.dat**

This file is plain text and only accepts a list of rules as provided below in your prefered order. '_word_' below is a text string (single word) that you want searched. The rules file also accepts comments and setting values for some user configurable [options](http://code.google.com/p/comicrack-duplicates-manager/wiki/UserConfiguration?ts=1297328384&updated=UserConfiguration).

### File contents and syntax ###

(_NOTE_: spaces & tabs can be used at will, but make sure you keep one statement per line)

  * **COMMENTARY** lines that start with '#' or any text after a '#' in the line

  * **OPTIONS** are set using the following structure. Options available are described in the [options wiki page](http://code.google.com/p/comicrack-duplicates-manager/wiki/UserConfiguration?ts=1297328384&updated=UserConfiguration).
```
             @   OPTIONNAME   VALUE
```

  * **RULES** are formed by two or more words, as described in the next section.


---


---


# Rules Available #


---


### Text search related rules ###

These rules search for _words_ in the comic field specified (filename, filepath, tags, notes, scan information). The last rules (text) search in all the previous fields.

Each rule keeps or removes the comics in which the _words_ are found (verbatim) in the specified field. Note that both, the _words_ and the field to be searched are converted to lowercase, so these rules are **not case sensitive**. Also, _word_ is somehow intelligent (for instance, if you enter c2c or ctc, it will search for both of them).

If you want to apply the rule over a text that has a space inside it, you can surround it with ". For example, if you want to keep all comics with _nice name_, you can use the rule `text keep "nice name"`.

You can also use more than one work. In this case the rule will match any of the works. For example, if you use the rule `text keep nice name` it will match any comic that has the word _nice_ or the word _name_ in it.

```
  filename    keep    _words_
  filename    remove  _words_
  filepath    keep    _words_
  filepath    remove  _words_
  tags        remove  _words_
  tags        keep    _words_
  notes       keep    _words_
  notes       remove  _words_
  scan        keep    _words_
  scan        remove  _words_
  text        keep    _words_
  text        remove  _words_
  filetype    keep    _words_
  filetype    remove  _words_
```


---


### Alternate covers related rules ###

These rules search for strings like "`(2 covers)`" in the comic filename (note that "`(both covers)`" is parsed as "`(2 covers)`"). There are two options:

  * if the `all` command is included, the rule will delete/move all the comics except the one with the higest number of covers explicitly included in the filename.

  * if the `some` command is used, the rule will keep all comics without that string, and only keep the one with the highest number of covers of those that do have the string.

```
  covers      keep    all
  covers      keep    some
```


---


### Filesize related rules ###

Rule that keeps the largest or smallest comic. It can receive an optional parameter with the percentage of the size. This means that any comic that changes that percentage to the largest/smallest will be kept.

```
  filesize    keep      largest
  filesize    keep      largest 10%
  filesize    keep      smallest
  filesize    keep      smallest 10%
  filesize    remove    largest
  filesize    remove    largest 10%
  filesize    remove    smallest
  filesize    remove    smallest 10%
```


---


### Pagesize related rules ###

Rule that keeps the comic with largest or smallest pages. It can receive an optional parameter with the percentage of the size. This means that any comic that changes that percentage to the largest/smallest will be kept.

```
  pagesize    keep      largest
  pagesize    keep      largest 10%
  pagesize    keep      smallest
  pagesize    keep      smallest 10%
  pagesize    remove    largest
  pagesize    remove    largest 10%
  pagesize    remove    smallest
  pagesize    remove    smallest 10%
```


---


### Pagecount related rules ###

The only rules worth discussing here are `pagecount keep noads/c2c`. These are used to search c2c and noads comics when they are not explicitly indicated in text fields (for which you could use 'text' rules). What these rules do is that they separate the comics in two groups according to their real pagecount, and keeps the ones with less (noads) or more (c2c) pages, and moves/deletes the rest. The groups are populated by finding a given diference of pages between the one with most pages in the lower group (noads) and the one with less pages in the higher group (c2c). This gap value is given by user option [[C2C\_NOADS\_GAP](http://code.google.com/p/comicrack-duplicates-manager/wiki/UserConfiguration?ts=1297328384&updated=UserConfiguration), and defaults to 5. If two distinct groups cannot be created, no ecomic is deleted.

The rules ` pagecount keep largest/smallest ` can receive an optional parameter with the percentage of the page count. This means that any comic that changes that percentage to the largest/smallest will be kept.

```
  pagecount   keep    largest
  pagecount   keep    largest 10%
  pagecount   keep    smallest
  pagecount   keep    smallest 10%
  pagecount   keep    fileless
  pagecount   remove  fileless
  pagecount   keep    noads
  pagecount   keep    c2c
```


---


### Other rules ###

Sometimes you have 2 exactly equal comics that are just in different folders. In this case you can use the ` keep first ` and it will keep the first comic in the list. Warning: It should be used only as a last resourt, because it will ignore everything and just keep the first comic in the duplicated group.

```
keep first
```