---
date: 2020-08-20 12:05:34+00:00
draft: false
title: Mobile R setup
type: post
url: /blog/2020/08/mobile-r
categories:
- Code
tags:
- R
---
This is a little post about how I use R when I want to make changes in my code or test things and can’t sit in front of a big screen.

I have installed the following:  
#### iMac (always on  
- R  
- SSH/[Mosh](https://mosh.org). To access my iMac from my iPhone. Just SSH works fine and you don't need to install anything but Mosh keeps the connection when moving between networks (Wi-Fi and cellular).
- [radian](https://github.com/randy3k/radian) An alternative console for R with multiline editing and rich syntax highlight (requires R, python).  

#### iPhone  
- [Textastic](https://www.textasticapp.com). Code editor to edit scripts.

- [Blink](https://blink.sh). An iOS terminal, with SSH and Mosh. I use it for Mosh, Textastic has built-in SSH terminal as well. I use it to connect to my iMac, start radian, run the scripts or test code in radian.  

#### iMac and iPhone  
- Synced folders (I use iCloud) where the scripts live and plots are saved as images.  
&nbsp;  
&nbsp;  

Simple workflow:  
1. Start an SSH/Mosh terminal on iPhone to connect to iMac.  
2. Start radian on iMac.  
3. Write code in radian and see the results in the terminal or export a simple plot as an image.  

&nbsp;  

When working with bigger scripts, I first write the script in RStudio on my iMac. When I want to write more code or change it on my iPhone:  
1. Edit the script in the code editor.  
2. Connect to iMac with an SSH/Mosh terminal and run the script in radian with source().  
3. If I make a plot, I save it as an image inside a synced folder and then view it with Files on my iPhone.

