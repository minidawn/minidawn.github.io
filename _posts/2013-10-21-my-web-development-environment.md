---
layout: post
date: 2013-10-21 19:02
title: "My Web Development Environment"
author: gosukiwi
---

I'm by no means a Vim or Ubuntu expert, nevertheless I've been developing websites for at least 5 years and I've tried quite some environment alternatives, but nothing beats **Ubuntu + Vim** so far.

To be honest, the environment highly depends on what technologies you use, for example if you are working on a ASP.NET MVC site, Visual Studio and Windows are probably the best environment.

I'm talking about open-source technologies, such as PHP, Ruby, Python, Javascript, Node... You name it!

# Why Ubuntu
I like Windows, I spend most of my day on Windows 7 (as I'm studying right now, not working), the main reason is I play **a lot** of League of Legends, I think the gamer part in me is almost as big as my programming part, so if I'm not programming, I'm gaming!

Nevertheless, If I'm about to develop, I grab my notebook, boot Ubuntu, open up a terminal and that's all I need! It's hard to beat that. (I don't even need a mouse! +1 for Vim)

## Ease of setup
Do you need to set up a PHP development environment? In Windows you'd need to open up a browser, google for apache, download and install it, then repeat for PHP and MySQL, and also don't forget to check the configuration! 

Of course there are alternatives which help you out a bit like XAMPP, but still, I find it nice **only** if you don't need to change any server configuration or use a CLI.

In Ubuntu? Just ```apt-get install``` all the way! You can then use ```a2ensite```, ```php``` and all those commands you'll surely need later on. Also if you are going to use a CLI, UNIX shell is much nicer than DOS and nobody uses Powershell.

## Deployment
It's always a good idea to make the development environment as close as the release environment as possible.

It's highly unlikely than a PHP (or Python, Ruby, Node) application will run on a Windows server, 99% of the time it will be a linux distro such as Ubuntu Server.

## Tools are designed to be used in UNIX
Going against the flow is good sometimes, but it won't be so easy as going with it, for example, you can use Symfony CLI in Windows, but in UNIX that just comes out of the box, all the parts play nice with each other as the developers also used UNIX to make them!

For example, installing a ruby gem which requires native compilation is a pain in Windows (for example when installing SproutCore).

# Why Vim
Vim is an awesome text editor with the disadvantage that it's quite hard to  learn how to use it effectively.

There are books, articles and tutorials on how to use Vim, I recommend [A byte of Vim](http://swaroopch.com/notes/vim/) by Swaroop C H to get a feel of Vim.

## Plugins
Most of the things you think it would be cool to have in Vim but are not into the core already exist in the form of plugins!

For a nice development experience I use the following:

 * NerdTree
 * ZenCoding
 * Powerline
 * EasyMotion
 * CssColor
 * FuzzySeach
 * Surround

Those give me all I need to make effective editing in my projects. On a later post I'll speak about my Vim setup and detailed info on each plugin. For now I just want to highlight the advantages over others.

## No mouse!
One advantage I really love when using Vim is that it needs no mouse, you'll find no big difference between desktop and notebok, and as you can do everything with Vim + Terminal!

## Open source
Vim is free and it's licence is GPL-compatible, no pop-ups like Sublime or other private editors.

## Effective editing
Once you are proficient with Vim, it's **very** movement-efficient, meaning with a few key strokes you can edit almost anything you need.

## Alternatives
If I can't use Vim, my second choice is Sublime Text, it really has beat every other text editor without counting the "big old two", Vim and Emacs.

It can use Textmate plugins and has a wide variety of awesome plugins! Most of my Vim plugins have an equivalent for Sublime Text, also, it supports **Vintage mode** which emulates Vim behaviour.

# Conclusion
All in all the efficiency of Vim for editing and the ease of use and terminal of Ubuntu make it really easy to develop web applications based on open source technologies.