---
layout: post
title:  "Welcome to Jekyll!"
date:   2013-11-10 10:18:00
categories: Post Mordem
---

Earlier in my career I was tasked with creating a UI widget that was powered by a 3rd party API. This was before the current craze of functional programming and underscore was just becoming a thing.

I like to look back at old programming challenges to see/cringe at the code that i wrote and also to see how i might approach a task now, given what i know now. 

What did i learn? Imperitive programming is a bitch. The code was originally started by another developer and we were under a tight deadline to glue the existing code to a new UI, I didn't want to completely rewrite it and uncover an untold amount of bugs or edge cases that the previous developer coded around. I also didn't like the endless amount of if statements in the code. But how could i do better?


**What I learned**

Get familiar with the data. So often you are in a rush to get started and code, but you can remove a lot of cruft from your code by having a clear understanding of the task at hand. This is painfully deceptive, because how many times have you thought you understood only to realize later you made a false assumption? It's really difficult to get a birds eye view without understanding the shape of the data you'll be working with.

Rarely do you have the opportunity to build from scratch. The more realistic case is that you are inheriting code from others or have to iterate on code that you wrote months or perhaps years ago. Resist the urge to rewrite, try to extend the existing code by creating new methods. This way you don't risk breaking existing functionality.

forms and buttons are a bitch. the more interactive a form the more use cases you have to support. validating data and use flows are unpredictable. while design loves throwing the words 'easy' and 'simple' around, it ultimately falls on you to implement it in a way that you and your team can debug and extend. no easy task. a form library can bring a ton of functionality out of the box and get your team productive rather than slowly learning the pitfalls of doing it yourself.

as a small addendum, functional libraries like lodash make data manipulation easier to reason about. Currying functions can help reusability when we have code that performs the same task on different inputs. However doing it by hand often means you have to remember the details of 2 call sites. the place where you passed the first value and the final call site:

function greetTheJetsons(lastName){
	return function(firstName){
		console.log('hello '+ firstName + ' ' + lastName)
	}
}
var hello = greetTheJetsons('Jetson');

/*
20 lines of code later, what type of parameter does hello take? imagine when its being passed in a complex JSON object with less than
semantic key names
*/

hello('George')
hello('Judy')
hello('ElRoy')
hello('Jane')
