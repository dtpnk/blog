---
title: "CLI - Logging im bash skript"
excerpt_separator: "<!--more-->"
categories:
  - DE
tags:
  - CLI
  - DE
  - log

header:
#  teaser: /assets/images/unsplash-code-01-150.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
#  actions:
#    - label: "More Info"
#      url: "https://unsplash.com"
---


folgendes Codeschnipsel am Anfang vom Skript bewirkt, dass die komplette Bildschirmausgabe (auch remote-Sessions) ins Logfile geschrieben wird.
<!--more-->
```bash
[...]
# Logging
LOG="/var/log/$(basename $0.log)"
exec > >(tee -a $LOG ) 2>&1

# Kosmetik / Header fürs Log
echo -e "\n---------------------------------------------------------------------------------------------\n
$(date) \n
---------------------------------------------------------------------------------------------" > $LOG
[...]
```



