# generate_wiki
Script to generate a wiki from md files.
It search all directories for md files and generates html pages for the found files. 
The directory structure is kept in the index page to easily identify and organize the pages. Each directory is seen as a chapter/heading in the index.

It also contains a black_list to exclude some directories if needed.

## How to use

### Example
As an example consider the following dir, which is the root of the wiki.


```bash                                                 
▶ tree -L 1
.
├── 1-Introduction
├── 2-Tools
├── other_information
├── tools_usage
└── wiki
```

The `wiki` dir contains all the generated html pages, and both scripts used to generate the wiki.


```
▶ ls *.* | egrep -v "html|img|png"
BuildBetterIndex.py
exclude_dir.lst
generate_wiki.sh
index_legacy.md
pages.lst
```

+ `index_legacy.md`: Is a legacy index generated by generate_wiki.sh and does not use the BuildBetterIndex.py script.
+ `generate_wiki.sh`: Main script which should be executed. It will call BuildBetterIndex.py 
+ `BuildBetterIndex.py` Generates the index in tree format
+ `pages.lst` List of all pages in the wiki. It is file to help the script keep track of the pages. DO NOT DELETE IT, it is used to backup the old files before generating the a new wiki.
+ `exclude_dir.lst`: List of dirs to be excluded

When running the script it will always generate an `old` dir where it stores a backup of the old wiki.


## Requirements

+ Pandoc
+ Python.



