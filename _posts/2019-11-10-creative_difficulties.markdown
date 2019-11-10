---
layout: post
title:      "Creative Difficulties"
date:       2019-11-10 12:39:16 +0000
permalink:  creative_difficulties
---


##I recently completed my cli application project. I chose to make a lighthearted little interface that allows for comparison of users of letterboxd, which is basically gooodreads for movies. It helps movie fans log movies, rate them, list them, etc. What I made allows for scraping of particular users’ profiles, but more specifically the movies they’ve rated, and displays those movies and what they rated highly. It also allows you to compare two users directly if you want to see if you and a friend agree on how good a particular movie was or if you want to show off how many movies you’ve rated relative to them. The journey to this point was slightly hazardous, but that just makes it a good learning experience.

###When it comes to cli projects in general, I was comfortable coming into this one. I was enamored of the tic-tac-toe game I built as part of regular coursework and I felt comfortable with the interface aspect.
I discovered a real need while doing this project to develop a strategy of reaching out for help. I’ve known for a while that I have real problems in this area, but I usually tend to ignore them. I think most people tend to ignore the problems that they face when it comes to their own habits and I’m a person myself. Self-reflection is a bit difficult in general, and proactive self-improvement is just a real stretch.

###My normal work pattern turned out to not be an ideal strategy for either finishing the project or finishing the accompanying video tutorial or blog. I tend to hyperfocus on whatever I happen to be thinking about. It’s just an effect of adhd, but basically it means I go dead to the world and think about one thing to the exclusion of all else if I think about it too hard. As a result, there were a few times during this project that I found I had about fifteen tabs open and had been spending several hours on work that didn’t need several hours to complete without asking for a single bit of help from my community of fellow learners and instructors.

###Now I know I have a problem with this, and it still happened. The strategies I’ve found for dealing with this are not always effective but whatever the specific strategy is, it has to have specific, measurable, and feasible benchmarks or I’ll probably forget it. This is still a work in progress for me; I tend to snowball hard from being productive and proactive in this area to falling into habits of forgetting that I have support and back very quickly. I think establishing relationships with others who can hold me accountable to the goals I set for myself is the key.
 
###In any case, I finished the project, and I’m proud of what I’ve accomplished. At the same time, I’m excited to see it improve over time with ample support from others as I grow accustomed to that. Without using my resources to the fullest, I did run into a few stumbling blocks but also managed to find some good solutions.

###Handling the user input was a simultaneously rewarding and humbling experience. I was particularly proud of applying the DRY dogma to my method I made for handling the basic input of my program. 

###Basically, I structured my interactive loop to always return to a main menu with a limited number of basic commands as input no matter what the user did. The only way to leave the program was to type ‘exit’ and the only real way to interact with the program was to type in one of about seven commands. A prompt showed the user the correct inputs if they struggled. 

###The way I handled this was to create a constant to hold an array of acceptable inputs and a humorously large method to translate input into a case statement which simply called the exact user input as a method but with underscores instead of spaces. Fortunately, about halfway through making this monstrosity, I got frustrated typing the same stuff repeatedly, and realized I was making a mistake. Ruby actually has, as it turns out, this lovely built in send method which does the same thing I was trying to do in about one tenth of the number of lines. 

###A good learning experience from this project also occurred when my partner agreed to test out my program days after the last time that I’d played with it, on my invitation, and managed to find a point in my program where the input wasn’t friendly to someone who hadn’t noodled around extensively in the code (i.e. anyone except me). The actual fix wasn’t that difficult since all I had to do was remove the case sensitivity for the movie title input by lower casing every individual word of input, but it showcased how a program that feels water tight to the person who writes it can actually be really vulnerable the second its interface gets in any way complicated. 

###In general, the project was fun and rewarding for me to take on, but the largest challenge has been in communicating what I’ve done and properly utilizing my community. I think the application I made is a cute little thing, and I know with a little bit of collaboration it could be a pleasure to use as well.


