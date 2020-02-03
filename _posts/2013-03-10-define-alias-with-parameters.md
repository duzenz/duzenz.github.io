---
title: "Define Alias with Parameters"
read_time: true
tags:
  - ubuntu
  - grep command
  - linux
  - alias
  - alias parameters
  - alias with parameters
  - unix
  - bashrc file
---

In my code bases I was always using grep command with a lot of parameters.

For example;
```bash
grep -ir --exclude-dir=".svn" --color "yourString" searchFolderName/
```
Everytime typing this command started to become annoying for me. 
For that reason I searched a solution for that problem and found an elegant way to achieve that.

Firstly open up your terminal and open file ".bashrc".  
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

You can give other parameters with $2, $3, $4