---
title: Adding WordPress Excerpts Without Stripping HTML
summary: A way to create excerpts without stripping out the HTML.
date: 2017-02-03
tags:
    - post
    - wordpress
    - tech
    - coding
---

This is by far not arcane knowledge, but it's something that I found while I was coding the site's new theme: a way to create excerpts without stripping out the HTML.

Why would anyone need this? Say you're like me, and you like lists of links to save for later or to share. You create a post, but your front page only allows excerpts by default. Your lists and links are now just a big pile of text with absolutely no sort of context.

This is the problem I ran into, so I did what any dev would do: I searched the web and ended up at StackOverflow. What I found was great -- it did everything I needed it to do with only a few modifications.

What it does is this: it strips shortcodes, applies a wordcount, and outputs the filtered content with the html tags in place. This was more elegant than my solution, which was to truncate the code via CSS and hidden overflows, which sometimes cut text off in strange spots.

The link to the StackOverflow solution is here: [http://wordpress.stackexchange.com/questions/141125/allow-html-in-excerpt/141136](http://wordpress.stackexchange.com/questions/141125/allow-html-in-excerpt/141136). The solution is nicely annotated with explanations of each block of code, so that you can understand how everything works as you read.
