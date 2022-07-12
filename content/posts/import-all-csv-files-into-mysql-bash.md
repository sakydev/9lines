---
author: "Saqib Razzaq"
title: "Import all CSV files into MySQL using BASH"
date: "2022-07-11"
description: ""
categories: ["bash"]
tags: ["mysql"]
ShowToc: true
TocOpen: false
---
This script iterates over a directory and imports each CSV file into specified MySQL table.  
1. Create a file `import.sh` and make it executable  
2. Paste following code in file  

```bash
DIRECTORY='input_directory'

for csv in $DIRECTORY/*.csv;
    do
        echo "Loading $csv"
        mysql -u 'username' --password='{password}' -D '{database}' -e "LOAD DATA INFILE '$csv' IGNORE INTO TABLE '{tablename} FIELDS TERMINATED BY '\t' ENCLOSED BY '\"' LINES TERMINATED BY '\n' IGNORE 1 LINES;"
    done
```