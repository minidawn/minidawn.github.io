---
layout: post
date: 2013-11-01 15:26
title: "So you want to write some Javascript"
author: gosukiwi
---

There are some things you must know if you are new to Javascript and want to use it in your web app.

## Just read a book on Javascript
There are lots of tutorials, but very seldom a tutorial quality is good enough, I cannot recommend **Javascript The Good Parts** enough, it's an awesome book which helped me re-learn a lot of Javascript.

If your first taste of Javascript is with that book, you'll end up saving **lots** of headaches.

Another book I'm reading and reccommend is **Functional Javascript**, those books give you a rock solid foundation for writing mantainable (as mantainable as Javascript can be) apps.

## Divide and conquer, use RequireJS
RequireJS implements a very important feature Javascript lacks, a "module" system. 

Using RequireJS you can include files in your Javascript source code and not in your markup, this is awesome for many reasons

 * Only load what you need when you need it
 * Load text files like templates
 * Minimize all of your app javascript

Beeing able to divide your app into several parts it's a basic and utterly important concept, and dividing your code into several files is one of the most basic forms of division.

## jQuery

jQuery is pretty much the best tool for DOM manipulation out there, it has a very intuitive API, and beeing so popular the support is as good as it can get, there is really no reason to not use jQuery.

## Use views
Separating view logic from application logic is very crucial when writing mantainable code, the easiest way is to use Handlebars, Mustache, Hogan, Underscore, or any other template library out here.

Using RequireJS' ```text``` plugin you can load and compile them dynamically.

## Frameworks are not always the best choice

If you are planning on building a huge client-side app, frameworks such as Ember, Backbone and JavascriptMVC help you organize your code and give you an awesome base to work on, nevertheless, if your app is not that big (which happens in most cases) you can get away with just using Require, jQuery and some very specific library you might need (Handlebars, Observers, Router, etc), that way you skip a learning curve and you can start coding right away!

Take the [Riot framework](https://moot.it/blog/technology/riotjs-the-1kb-mvp-framework.html) as an example, basically everything the framework does is give you an ```observable``` function which enables you to observe a Plain Old Javascript Object (POJO), it includes a router and a way to render html views.

That's nice, nevertheless you'll find out that it's just a way to organize your code, you can use third party libraries for everything the framework provides, and have a nice and lightweight MVP architecture for your app.