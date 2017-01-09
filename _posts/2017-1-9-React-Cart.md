---
layout: post
title:  "React Cart"
date:   2017-1-9 10:18:00
---





[**A Product Page Built in React.**](https://imrob.github.io/cart/index.html)

**Why is this interesting or noteworthy**?

I wanted to kick the tires a little more and start building something a bit more complex and ambitious than the standard React app tutorial. While most React tutorials focus on data heavy applications, I've noticed that they frequently don't provide guidance on how to manipulate the DOM, which designers are still used to and will often ask for tweaks here and there within a UI.

Under a different paradigm, this is a simple job in a jquery tool belt, but can get interesting in React because of the parent child relationships of components. What happens when you need a modal box or a component that reacts in response to a click on a nested sibling? In my example a product may come in a number of colors and sizes, so we have to hide/show information based on the users action (showing what sizes are in stock). But when a user does click buy, we update the shopping cart component which is located at the top of the page. (Do we just keep passing down click handlers from a top level component?). Most of the time you want to go up a level and find a common ancestor and attach UI state there, but depending on what you need to build, this can get nasty quick, and you feel yourself perhaps cutting against the grain of what React is best for.

I feel this isn't talked about alot in the industry. React provides their CSSTransitionsGroup as a helper for CSS based animations, while React-Motions requires a strong cup of coffee and patience for most developers used to the old way of doing things. IMHO both are a bit involved for something that has been such common part of front end for years.

I'd be interested in hearing from other devs who have used react with animations and UI events that fall outside of parent/child relationships and how they structure state/event handlers in their apps.




