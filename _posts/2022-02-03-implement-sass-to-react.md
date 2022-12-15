---
layout: post
title: "How to use Sass with React JS"
thumbnail-img: /assets/img/2022-02-03/css-img.png
date: 2022-02-03
last-updated: 
tags: reactjs scss javascript programming
---

Although it might seem a little complicated at first it is actually quite simple. Here are the steps to get you started (assuming that you used create-react-app for your app).

## 1. Install sass using npm
To install the [sass](https://www.npmjs.com/package/sass) package and save it as a dependency, run:
```
npm i sass --save
```
The latest version of `sass` should be installed and listed in the `package.json` file. 

## 2. Create sass files
Now that you have `sass` installed, you can now use it in your application. Additionally, do not forget to import the stylesheets into your application. How I go about doing this is creating an `scss` folder (which will contain all of the stylesheets) inside of the `src` folder. I then import all of the styles in the folder into a single file (`styles.js`) so that I can import it into the root component of my app (`App.js`). Here is an example: 
<script src="https://gist.github.com/ismaeltovar/918b15909857e55630178faab6ee7e22.js"></script>

That is it! If you would like to see a working example of how to implement this, [check out this calculator I made using sass](https://github.com/ismaeltovar/awesome-school-calc).

Note: If you did not use `create-react-app` to create your application, you will need to find another way to use `sass`. One way you could do this is by installing the `sass` package on your system and making a custom script in your application to compile any `sass` files in your project. The [official docs](https://sass-lang.com/install) may be helpful if you need more assistance.

I hope this article helped. If you find an error or typo in one of my articles, please let me know.

**NOTE: I AM NOT LIABLE FOR ANY DAMAGES THAT HAPPEN BECAUSE OF YOU FOLLOWING ONE OF MY ARTICLES. This is not to say the information here is incorrect. Please be careful.**

Thumbnail image source: [source](https://pixabay.com/illustrations/logo-css-css3-icon-2582747/)