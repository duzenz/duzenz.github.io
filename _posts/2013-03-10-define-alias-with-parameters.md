---
layout: post
title: Define Alias with Parameters
date: '2013-03-10T23:30:00.000+02:00'
author: duzenz
tags:
- ubuntu
- grep command
- linux
- alias
- alias parameters
- alias with parameters
- unix
- bashrc file
modified_time: '2013-03-11T11:11:29.520+02:00'
blogger_id: tag:blogger.com,1999:blog-3877622808717317656.post-2613934672404225426
blogger_orig_url: https://duzenz.blogspot.com/2013/03/define-alias-with-parameters.html
---

In my code bases I was always using <b>grep</b> command with a lot of parameters.

For example;
```bash
grep -ir --exclude-dir=".svn" --color "yourString" searchFolderName/
```
Everytime typing this command started to become annoying for me. 
For that reason I searched a solution for that problem and found an elegant way to achieve that.

Firstly open up your terminal and open file<b> ".bashrc"</b>.  
After that paste the below code at the end of the file.
```bash
custom() {
    grep -ir --exclude-dir=".svn" --color $1 searchFolderName/
}
alias mygrep=custom
``` 

Save the file and type
```bash
source .bashrc
``` 
to command line.

Then you can use your new alias with parameters. 

```bash
mygrep "yourString"
``` 

You can give other parameters with <b>$2, $3, $4</b>