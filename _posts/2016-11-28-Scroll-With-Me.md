---
layout: post
title:  "Scroll With Me"
date:   2016-11-28 10:18:00
---

The other day I was looking for black friday steals and came across some janky scroll behavior. The page would stutter. I wasn't sure if it was just my computer or not, so I asked my wife if she saw the same thing on her machine. She did. I opened an incognito window and disabled extensions. Still there. Hmm.


![alt text](/assets/images/rl_sg.gif "Logo Title Text 1")


I fired up dev tools and started to take a peak. Figuring out performance issues on animations and scroll events is difficult because so many unrelated things can be a cause and the scroll event fires a ton. My first thought was to go to the timeline and record the behavior while i scrolled. Which lead to this:

![alt text](/assets/images/breakpoint.png "Logo Title Text 1")

A ton of scroll events, not shocking, but then looking at the call stack I realized how many scripts were listening to the scroll event.

We have in house UI functionality and 3rd party partners all querying the DOM for data anytime a scroll event happens. This is expensive. In their defense, they did try to throttle their events, but no amount of throttling is going to make up for so many scripts listening to such an active event. I've been behind that gun and its hard to argue with business when you have to implement a less than ideal 3rd party widget. Pick your battles.

The interesting part came when i drilled into a particularly active 3rd party script. It wasn't even looking for scroll events, it was looking for **ANY** event. Any time you moved the mouse, scrolled...sneezed it fired. Worse, it was being fired from within 2 closures, which means that nothing in these larger functions can be garbage collected since their environment needs to be reachable by any inner functions (and those closures contained a ton of methods and nested objects which also have to be maintained). 

The memory allocation timeline confirmed a massive buildup. I'm sure there may be a solid technical/business reason for this, but remember, my little adventure began because my page was hiccuping every time I tried to find product. This was a customer facing problem compromising the core functionality of a webpage.

Clearly this script is doing analytics on how users interact with the page, but why track every little thing the user does? At some point I'd think there would be a law of diminishing returns with such a large data set. I get tracking clicks or even how far down a page a user scrolls, this has clear actionable business use.

But hey, i'm just a curious developer poking around dev tools and those decisions are above my pay grade.