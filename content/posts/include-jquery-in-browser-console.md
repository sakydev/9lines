---
author: "Saqib Razzaq"
title: "Include jQuery in browser console"
date: "2022-07-11"
description: ""
categories: ["jquery"]
tags: ["browsers"]
ShowToc: true
TocOpen: false
---
jQuery as we know comes loaded with most websites today. However, if there is a case when you'd like to run some experiments on website using jQuery but it isn't being load by default, you can run following command

```javascript
var jq = document.createElement('script');
jq.src = "https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js";
document.getElementsByTagName('head')[0].appendChild(jq);
// ... give time for script to load, then type (or see below for non wait option)
jQuery.noConflict();
```