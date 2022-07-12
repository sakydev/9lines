---
author: "Saqib Razzaq"
title: "ZIP All Files in Directory and Send to Another Server in Bash"
date: "2022-07-11"
description: ""
categories: ["bash"]
tags: ["devops"]
ShowToc: true
TocOpen: false
---
First install `zip` if not already installed

Ubuntu `apt-get install zip`
Centos `yum install zip`

Then create a `file.sh` and paste the following code

```bash
OUTFILE=outputfile.zip
INPUTDIR=inputdir
zip -R $OUTFILE $INPUTDIR
scp $OUTFILE usrename@outserver:/path/of/ $OUTFILE -i key.pem
```