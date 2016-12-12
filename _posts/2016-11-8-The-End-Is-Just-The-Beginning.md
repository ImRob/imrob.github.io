---
layout: post
title:  "The End Is Just The Beginning"
date:   2016-11-8 10:18:00
---

I'm writing this shortly after a site redesign while somethings are fresh in my brain. Maybe i'll come back and look at this one day when in the midsts of a similar task.  What did I learn? What is the one thing i can take away from this expereince that can help me grow as a developer and a team member?

One thing I keep harping on is the end is just the beginning. We don't know what we need when we build. Only the market does and they ultimately are the ones that validate all of the discussions we have in internal meetings and quick chats. We can think a feature is must have and obsess about it only to have the market return a collective, meh.

Often design will give me a UI and I implement it and we go back and forth a few times to iron out some rough spots, but we do so with a static document as our source of truth. The document represents the authoritative end. The redesign is finished when we accurately satisfy the graphic hierarchy of the document as well as any business logic. Then users test things and you have to iterate...and pivot...and the cycle starts.

This used to bother me, but I've come to realize that this is just the nature of the beast. It's better to embrace it and have it work as a built in part of your design process. The pain comes when you spend so much time amongst yourselves trying to get things just right, to the point that your code suffers. What started as a square, was slowly given rounded corners, turned into a circle but now needs to support bezier curves.

This is one of the problems with inheritance paradigms. It's difficult to accurately model real taxonomies because taxonomies are really really difficult to reason about. So let's stop. Realize we don't have a clue. We have hunches and really good guesses but no one really knows. And because of that it's best to understand that when given a goal its just the beginning, aim to make your code as extensible, unopinionated and malleable as possible. You'll thank yourself.