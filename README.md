# Python script to find duplicate files

This script is meant to be used interactively (I use it in IPython console). It checks for duplicates inside a given path
using md5sum hash.

It has the following main functions.

1. **`find_dup(path = '.', opt = 0)`**

  Find duplicate files in a given path (or files in the directory tree rooted at this path) by md5sum hash.
  
  Options: If `opt = 0` (default) it checks files immediately in the path (and not its subdirectories). If
  `opt = 1` it checks all files in the directory tree rooted in the path.
  
  Returns: Two dictionaries `(md5_dict, dup_count)` where `md5_dict` is a dictionary with md5sum as keys and
  file name(s) as values (if `opt = 0`), or file path(s) as values (if `opt = 1`); and `dup_count` has md5sum
  (of duplicate files) as keys and the number of _redundant_ duplicates as values.  So if a file occurs twice,
  then the duplicate count is 1.

2. **`dup_summary(md5_dict, dup_count)`**

  Print a summary of duplicate files, using the outputs from the `find_dup()` function.
  
3. **`dup_report(md5_dict, dup_count)`**

  Print a detailed report of duplicate files, using the outputs from the `find_dup()` function.
