---
title: "CLI - Suchen und Löschen in der Konsole"
excerpt_separator: "<!--more-->"
categories:
  - DE
tags:
  - CLI
  - DE

header:
#  teaser: /assets/images/unsplash-code-01-150.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
#  actions:
#    - label: "More Info"
#      url: "https://unsplash.com"
---

Dieses Vorgehen benutzt man, um bestimmte Dateien zu suchen und gleichzeitig auch zu löschen.

Allgemeine Syntax:

```
find <dir-name> <criteria> <action>
```
<!--more-->
* `dir-name`: - Defines the working directory such as look into /tmp/
* `criteria`: Use to select files such as „\*.sh“
* `action`: The find action (what-to-do on file) such as delete the file.

jetzt genauer:  
löscht Dateien\_und\_Ordner:

```
find . -name "FILE-TO-FIND" -exec rm -rf {} \;
```

löscht nur Dateien:

```
find . -type f -name "FILE-TO-FIND" -exec rm -f {} \;
```

* `-name „FILE-TO-FIND“`: File pattern.
* `-exec rm -rf {} \;`: Delete all files matched by file pattern.
* `-type f`: Only match files and do not include directory names.

Mit`-iname`anstatt`-name`kann man auch Wildcards wie`?`oder`*`benutzen.

##### Bsp.: {#bsp}

`fo*`und`F??`→```Foo``,```FOO```,``foo`,`fOo\`, etc

> Die Befehle mit Bedacht einsetzen, sonst werden ungewollt Dateien gelöscht
>
> Vorher besser mit`find . -name „FILE-TO-FIND“`_ohne_`-exec rm -rf {} \;`überprüfen, ob die Syntax stimmt.

## Links {#links}

* [http://www.cyberciti.biz/faq/linux-unix-how-to-find-and-remove-files/](http://www.cyberciti.biz/faq/linux-unix-how-to-find-and-remove-files/)



