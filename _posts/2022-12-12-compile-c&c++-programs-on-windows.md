---
layout: post
title: "A simple way to compile and run C/C++ programs on Windows"
date: 2022-12-12
last-updated: 
tags: linux windows bash c/c++
---
A couple of weeks ago I broke my Linux installation on my computer because I downgraded to an older version of `valgrind`. Since I did not find a solution promptly and I had homework assignments to complete, I decided to work on my Windows installation in the meantime. Although I could complete my assignments on a virtual machine running Ubuntu, I wondered if there was a better way to go about the compilation and running of C/C++ programs on Windows locally. I had heard about [MinGW](https://www.mingw-w64.org/) in class, but I wanted to see if there was anything online with more Linux package support available. I eventually stumbled upon [Cygwin](https://www.cygwin.com/). Although it did take longer to compile code, it was not significant enough to deteriorate my workflow. However, `valgrind` was not available for Cygwin, which still prompted me to boot up a virtual machine now and then whenever the infamous segmentation faults came to say hi. I wondered if there was yet another way to compile C/C++ almost as if I were on Linux. Because I did not find a solution in the limited time I had, I stuck to working with Cygwin and a Virtual Machine to get through the semester. 

But then, this weekend as I was downloading a Ubuntu ISO file for my Ventoy installation, I found out about WSL (Windows Subsystem for Linux), which allows me to run a Linux terminal environment on Windows. I was immediately mindblown. Canonical's website (the creators of Ubuntu) describes two ways one can go about [installing WSL on a Windows system](https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-11-with-gui-support#1-overview). I followed the command line method as I found it much simpler and geeky. 

All I had to do for the command line method was open PowerShell and run `wsl --install` and wait a couple of minutes. After the installation was complete, I rebooted my system, and voila, now I can compile and run C/C++ programs as if I was on Linux! Any packages I needed to install on a Ubuntu machine could now be installed on WSL, including `valgrind`, using good old `apt get`.

Soon after, I realized that it would be very useful if I could configure the default path of the WSL terminal. Since I could do a similar thing on Cygwin, I looked up online to see if this was the case. [I stumbled upon the Windows Terminal](https://stackoverflow.com/questions/59057687/how-to-change-default-directory-in-windows-subsystem-for-linux), which I found extremely useful not just for WSL, but for running any terminal session in general. Once the Windows Terminal is installed from the Microsoft store, one can configure the default path of WSL in two ways. The first method is to modify the `startingDirectory` property in the `settings.json` file, which can be accessed by pressing `CTRL + SHIFT + ,` on a Windows Terminal session. The second method is to go into the GUI settings in the Windows Terminal by pressing `CTRL + ,` and modifying the setting highlighted below:

![Ubuntu WSL settings Windows Terminal](/assets/img/2022-12-12/windowsTerminal.png)

One can set the default path to any folder on any drive on a system by replacing the `/c` directory after the `/mnt` with the appropriate drive letter.

Thank goodness cross-platform applications exist.