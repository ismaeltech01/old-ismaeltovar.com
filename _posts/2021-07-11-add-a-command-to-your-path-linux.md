---
layout: post
title: "How to add a directory to your PATH on Linux"
thumbnail-img: /assets/img/2021-07-11/console.png
cover-img: 
date: 2021-07-11
modified_date: 2021-09-13
tags: linux bash
---

So, you decided to download a package or program in order to complete some useful task. However, once you run the command to run the package, you get an error that looks something like this:

```
bash: command not found
```

Wait, but you just installed the package! Why does it say that it is not there?

You may be getting this error because you don't have the directory that contains the command in your PATH. This may seem more complicated than it sounds, but adding a directory to your PATH is actually really simple. Here are the steps to adding a directory to your PATH.

## Search for the .bashrc file

In order to add a directory to your PATH, you need to locate the `.bashrc` file. It's usually located in the Home directory. To search for the `.bashrc` file in the Home directory, type the following commands in the terminal:

```
cd ~
ls -a | grep '.bashrc'
```

If the file is in the Home directory, you will get an output of `.bashrc`. If you get an output other than `.bashrc`, then that means the file is missing. Fixing this error is a bit beyond the scope of this article, so i'll be best if you type 'missing .bashrc file linux' on Google and see what you can find.

## Edit .bashrc

Next, you will need to edit the `.bashrc` file. Open the file with your text editor of choice or type the following command in the terminal:

```
nano .bashrc
```

Scroll to the bottom and add the following line at the end of the file:

```
export PATH=$PATH:/path/to/folder/with/command
```

To give you an example, if I would like to add the `bin` directory in the `VSCode-linux-x64` directory PATH:

```
export PATH=$PATH:/home/ismael/VSCode-linux-x64/bin
```

If you don't know which directory contains the command you want, try looking for a directory named `bin` in the root directory of the command's package. That is where you will usually find the commands installed with a package.

Save the document and exit the editor (`Ctr+S` then `Ctr+X` if you used the `nano` command above).

## Verify that the command is in your PATH

Close the terminal window and open another terminal window to get a new terminal instance. To check that the command is in your PATH, type the following into the terminal:

```
which command
```

`command` being the name of the command inside the directory you added to your PATH using the above steps

If you get an output that looks something like this:

```
/home/ismael/VSCode-linux-x64/bin/code
```

Then you have successfully added the directory to your PATH! You should be able to run the command without the `bash: command not found` error anymore.

If you get an output that looks something like this:

```
which: no code in (/file/path:/file/path)
```

Then too bad, so sad. You have failed your job. Jokes aside, open `.bashrc` and double check that you did not accidentally missed a typo when you added the `export PATH=$PATH` line at the end of `.bashrc`. Additionally, check that you typed the file path correctly (FYI, `/` stands for the root directory). If you need more help with file paths in Linux, [here is a useful website that can help](https://opensource.com/article/19/8/understanding-file-paths-linux).

I hope this article helped! Make sure to share this article with someone who might find it useful. If you find an error or typo in one of my articles, please let me know.

**NOTE: I AM NOT LIABLE FOR ANY DAMAGES THAT HAPPEN BECAUSE OF YOU FOLLOWING ONE OF MY ARTICLES. This is not to say the information here is incorrect. Please be careful.**

Thumbnail image by source: [https://pixabay.com/vectors/bash-terminal-linux-unix-computer-161382/](https://pixabay.com/vectors/bash-terminal-linux-unix-computer-161382/)