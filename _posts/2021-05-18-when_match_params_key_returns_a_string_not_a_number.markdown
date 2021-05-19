---
layout: post
title:      "When match.params.key returns a string, not a number"
date:       2021-05-19 00:17:21 +0000
permalink:  when_match_params_key_returns_a_string_not_a_number
---


Writing a small React project for the first time can be a little bit intimidating as there’s a lot to keep in mind. For me, I was worrying about how thunk would work, for example. Before starting, I was only really comfortable in my ability to use it to fetch data, but not to post. There were other things as well that I was worried about, including trying to make my components as simple as possible, with as many functional components as I could get away with given my current knowledge of react, as well as keep my components as stateless as possible. There’s a lot of little things that you can worry about is what I’m getting at, but sometimes it’s the really simple misunderstandings about how the framework works that can be the most frustrating, and not the bigger conceptual problems.

To get a bit specific, I was using the react router dom package and trying to set up some client side routing. This is definitely one of the areas that I had less experience in, even relative to other react concepts and conventions. Still, I had some confidence in my understanding of it. I felt like I understood routes and path matching and I was using them along with navlinks to set up a few pretty simple static routes. Then, however, I decided to set up a few resource routes programmatically. The way I decided to do it in my case was to pass down the routerProps to a container child component as well as a whole collection of that resource, which I intended to iterate through using the match params. This approach did end up working for me but it caused a real headache at one particular pain point.

The first thing I did was confirm that I had access to the :id from the url; I did have that. Then I made sure that I had access to the collection of my resource (in this case, I had a collection of decks that each held a collection of flashcards); I did have that. Perfect! I then hard coded CardsPage component that I intended to use as a container component for one particular deck to use the first deck in the collection while I built the layout and tested it out. All was well. 

It finally then came time to put the routerParams that I had bothered passing down to use. I iterated through the decks collection just using js find. My poor little project immediately broke. Since the problem was definitely related to my use of find, I obviously wondered how I had misunderstood this very basic javascript method that I had successfully used many times before so horribly. I looked at the docs, just to make absolutely sure that this method used a callback function and that each member of the collection would be passed in. That is how it’s used, so that search calmed me down just a little bit with regards to my understanding of find, and only stressed me out by about the same amount by highlighting how little I understood of what was going wrong. 

Sometimes, when I come across a problem, I trust the wrong things. In this case, I did trust that my callback function was totally fine. This is the callback function I chose to trust:

```
const deck = props.decks.find((deck) => deck.id === id)
```

I trusted this function because I’d used this exact function in other very similar situations. I trusted it because if I tried it out in the console, setting the id variable equal to the number that it was in the url directly, it worked. I trusted it because you can find this exact callback function being used in tons of examples on the internet if you google how to solve this exact, very simple problem. I trusted it because I understood every part of it and couldn’t imagine what was going wrong; I had to be using the wrong method, maybe, or maybe I’d unhooked the decks from props, or something similar and equally annoying. 

It took me quite a while before I realized that it really was the callback function, and that the solution was both really simple and really silly. I simply hadn’t realized that the id in the code above was not a number at all, but a string. This is how I was accessing the url:

```
const id = props.match.params.id
```

This line of code gave me an id that was a string. Simple as that. So, the comparison operator === that I was using in the callback was returning false. That’s it.

 It was a lot of consternation within a framework I didn’t fully understand and it made me doubt basic Javascript. And it wasn’t even react that I was having trouble understanding, it was just the react router dom package and its routerProps. All I had to do was change type to a number or change the operator to a ==, and this problem really give me a headache and cause me to narrow my focus on things that I thought maybe I didn’t understand but in fact totally did, and to completely overlook the one part of the equation that I hadn’t used extensively before. All in all, it maybe was a frustrating experience, but without question I’ll be having similar experiences again, and I think it’s simply a lesson in trying to trust myself with what I do know and to recognize a little better what I don’t.

