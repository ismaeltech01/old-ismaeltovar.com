---
layout: post
title: "Simple way to block websites on any computer"
thumbnail-img: assets/img/2022-07-29/blockedWebsiteError.png
cover-img:
date: 2022-07-29
last-updated: 
tags: linux windows self-help
---

Ever wanted to stop yourself from surfing the internet mindlessly? Well today, I am going to show you how. Although you can use browser extensions to perform this task, there may be some [privacy implications](https://www.howtogeek.com/188346/why-browser-extensions-can-be-dangerous-and-how-to-protect-yourself/). Additionally, they only work for the particular browser that you installed it on.

Here are the steps:

## Locate the `hosts` file

This will depend on your specific operating system. If you are using Linux or MacOS, the file should be located under `/etc`. If you are using Windows, it should be located under `C:\Windows\System32\drivers\etc`.

## Edit the `hosts` file as root/administrator

You can not edit the hosts file as a regular user, so you have to edit with root/administrator privileges. Afterward, you will need to add the following line to the end of the file:

`127.0.0.1 host_name`

`host_name` being the website you would like to block. The `127.0.0.1` represents the `localhost`, which is just your computer.

To give an example of how you would go about it, if you would like to block `youtube.com`, the line that you would have to add would look like this:

`127.0.0.1 www.youtube.com`

It is important to note that this may not work if you travel to a website that has a subdomain other than `www` or that has no subdomain at all. To fix this issue, you should also add the website with the appropriate subdomain, like so:

`127.0.0.1 youtube.com`

## Restart your browser/computer

Once you are done editing, save it and restart your browser by closing all browser tabs. If you try to navigate to the website that you added, you will get an error page that looks something like this:

![blockedWebsiteError.png](/assets/img/2022-07-29/blockedWebsiteError.png)

And as easy as that, you've got distracting websites blocked for as long as they are in the host file. If the website is not blocked, try restarting your device.

Thank you for reading and don't let the internet eat your time!