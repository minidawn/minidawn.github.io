---
layout: post
date: 2013-12-31 01:20
title: "Getting the Math Right"
author: about
---

The article width on Markdawn is exactly 608px. It's a multiple of 16, the base font size on the web. It's also exactly 16*2 less than 640px, the standard image width on the web and Instagram.

Matching 608px wide text content with 640px wide image is a little bit tricky, but it gives [a nice visual feedback](/post/1/) to the reader. The CSS code to do this looks something like this:

    .content {
        width: 608px;
        margin: 0 auto;
        }
        .content img {
            width: 105.25%;
            height: auto;
            margin: 10px -2.63%;
            }

For iPhone we have to recalculate both the content and image widths:

    @media (max-width: 320px) {
        .content {
            width: 90%;
            }
            .content img {
                width: 111.11%;
                margin-left: -16px;
                margin-right: -16px;
            }
        }

Get the math right folks, because it *hurts* without it. I use math to give more vibrancy to Markdawn design, thinking outside of box and placing controls on margins of content area. As a closing argument and also as future reminder: always remember who you are building the product for.