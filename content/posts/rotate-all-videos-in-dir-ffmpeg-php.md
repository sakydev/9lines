---
author: "Saqib Razzaq"
title: "Rotate all videos in directory with FFMPEG in PHP"
date: "2022-07-11"
description: ""
categories: ["php"]
tags: ["ffmpeg", "videos"]
ShowToc: true
TocOpen: false
---

```php
<?php
    $input_dir = 'dir';
    $output_dir = 'dir';
    $degress = 360;

    $files = glob("{$input_dir}/*.mp4");
    foreach ($files as $key => $file) {
        $filename = pathinfo($file, PATHINFO_FILENAME); // outputs nameonly
        $command = "ffmpeg -i {$input_dir}/{$filename}.mp4 -c copy -metadata:s:v:0 rotate={$degress} {$output_dir}/{$filename}-out.mp4"
        shell_exec($command);
    }
?>
```