---
author: "Saqib Razzaq"
title: "Run a script if it is not already running in Linux"
date: "2022-07-11"
description: ""
categories: ["bash"]
tags: ["linux"]
ShowToc: true
TocOpen: false
---
Let's say you have a script called crawl.py and you never want two instances of it running at the same time. The following script can do the job

```bash
RUNNING="$(ps aux|grep crawl|grep -v grep|wc -l)"
if [ $RUNNING -eq 0 ]
then
    python crawl.py
else
  echo "Already running : skipping";
fi
```