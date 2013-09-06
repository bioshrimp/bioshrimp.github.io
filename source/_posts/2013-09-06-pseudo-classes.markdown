---
layout: post
title: "Pseudo Classes"
date: 2013-09-06 15:25
comments: true
categories: [tutorial, css, pseudo classes]
---

I am still not able to solve my rails error so I am spending more time on learning about CSS. This is probably very basic knowledge, something frontend developers do in their sleep, but I feel pretty "Wheee" now that I am able to target certain list items.

**:nth-child** will target child-elements based on their position. 


For example I have an unordered list and want to add a styling only to the third list-element. All I have to do is pass the number 3 into the parenthesis : 

<pre><code>li:nth-child(3) {
	color: white;
	background-color: black;
}
</code></pre> 


I can even do more with using _expressions_ such as: **(an+b)**.


<code>b</code> will determine the start-position
and <code>a</code> will then select every "_put a number here_" element on top of that. We don't have to worry about <code>n</code>, it will just stay the way it is. Example: I have an unordered list and want to apply a styling to the third list item AND every 2nd item from that point on. I would use the **(an+b)** formula and just pass in my numbers 2 (for <code>a</code>) and 3 (for <code>b</code>). 

<pre><code>li:nth-child(2n+3) {
	color: white;
	background-color: black;
}
</code></pre>

 This would then look something like this: 

![Alt text](https://monosnap.com/image/apdIIHRQbbcK8bipENAVtm0hH.png)

Cool stuff! Haha. 