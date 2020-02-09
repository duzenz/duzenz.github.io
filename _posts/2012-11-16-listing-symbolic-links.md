---
title: "Listing All Symbolic Links in a Folder"
read_time: true
author: duzenz
tags:
    - symbolic links
    - bash
    - unix
---

The following code is listing all the symbolic links in a folder recursively.  

```bash
find . -type l
``` 

When you run this code in a folder, all the symbolic links in the folder listed as follows  

```bash
./app/design/adminhtml/default/default/layout/profile.xml
./app/etc/local.xml
./app/code/local/TTC
./app/code/local/Creare
./app/code/local/RichardMason
./app/locale/tr_TR
./lib/tcpdf
```