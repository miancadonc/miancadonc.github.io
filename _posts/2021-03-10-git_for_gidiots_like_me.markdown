---
layout: post
title:      "Git for gidiots like me"
date:       2021-03-10 21:25:18 +0000
permalink:  git_for_gidiots_like_me
---


### Most of this post is a justification for learning how to use git to a reasonable degree, even if you’re not yet part of a team where version control is important. Of course, the fact that it’s required on a lot of projects and is simply a good habit is also a good reason, but if this post personalizes git for you, then that’s good as well. At the end is a simple listing of really important git commands in one place, so hopefully if you’re like me and finished that module and still googled every command, you only have to look at this one resource to get a basic sense of how to use it. If you’re convinced of git and just want to see all of the commands I use (currently!) in one place, just skip to the end.

While working on my rails project, I was seized with the realization that at any given moment I didn’t know what to do.

Of course, from the beginning, I knew that I had a few specific tasks: I’d have to choose the models I’d be using, generate migrations to put their tables in my database, generate controllers and views for them, route everything up, and design some lovely nested forms and whatnot. I’d have to figure out which were my join models, which models could carry which attributes and which associations, and generally speaking I’d have to decide how the models would be accessible to the user of the app as resources. That’s a lot of things to think about, so even if I planned, and even if each individual decision was simple, the whole process could seem to be a bit complex.

Speaking broadly for a moment, I think that it’s times like these that really sap your motivation. Most people think they don’t like work, but I think that most people actually really like work, and it’s decisions that stymie us. Of course, you don’t want to work too much, but everyone feels better after getting a little something done. Everyone likes to feel like they’re on a roll! Maybe when something is frustrating, or unengaging, or unpleasant, we put it off, but how many times has just doing that task felt much better than we thought it would? 

Decisions, on the other hand, can be paralyzing if you think about them too much. The trick is to know when to dive deep and when to just get started and fix problems as you make them.

Giving in to the impulse to analyze each decision can be extremely beneficial of course - you need to know, for instance, how your app functions on the database level before your start to make a nested form. It’s important to know, for instance, if you want addresses to be an object of their own, rather than an attribute on a person or user object. It’s only so annoying to nest one finished form inside another, but to redo all of your migrations, maybe dropping your database and remaking it, and generating a new controller or remaking another one all make it more complicated than just taking one form and nesting in another.

That impulse can also lead you astray, though. Imagine spending hours agonizing over whether in your app’s context, it makes sense to make a tag object, and then whether that object should be a public resource or one that belongs to a user. You might say that if it’s a social site, then of course it should belong to a user! For example, if it’s an application for posting reviews of comic books, then each user being able to tag their own reviews would be very useful. But if everyone’s using the same tags, and they can look at everyone’s tags but those tags aren’t specifically tied to other users’ tags of the same name, then you lose out on a social function, and you have to store lots of tags of the same name in your database. If they’re not associated with each user, then maybe you save a lot on the database side, but you have to give out a limited number of tags for use. Even if you allow admin users to add or remove tags, other users will need to request a new tag each time they want one. 

That problem is probably not all that sticky, but if you run into worse ones, you might spend hours agonizing over details and not simply writing something and seeing where it breaks. Most coding should be about bug fixing and iteratively improving something; it’s not productive to try to make something perfect on the first try anyway if you’re going to need to maintain it, especially if you’re worrying so much that you don’t really get it done.

So, on to git. Most of the time, people will tell you that git, as version control, is especially useful for team based contexts. It allows for people to be working on different parts of the project without interfering with each other. They can break the project all they want, and there’s still the master branch to fall back on. It also gives people credit for their work whenever they commit. It’s great stuff!

When you’re working alone, though, of course you have to use git. You get into the habit, and you make sure you’ve got a branch that works, and you try not to break everything every time you add a new feature. But more importantly that that, for me, is that git makes the opportunity cost of making a new decision much, much lower. You won’t break everything, because the moment you wanted to work on a new feature you made a new branch. You can try two different answers to the same design question side by side if you want to! 

Another advantage of git in avoiding the creep of procrastination is starting multiple branches from master and having them going at the same time. Are you having a terrible time implementing omniauth because you haven’t realized yet that they updated to a new version? Don’t waste multiple days troubleshooting something that’s not even part of your application! Just work on a different part of the project for now, and come back to that thorny issue with fresh eyes. No, that didn’t happen to me. I don’t know why you’re asking. 

Git’s also incredibly useful for picking up where you left off in a project if you’re suddenly forced to take a break of a couple days because your favorite anime dropped a new season. I never really used the log command before this project, and that’s mostly because my commit messages were not as informative or consistent as they should have been, but git’s self-synergy is powerful, and the commits that I submitted like mad during this project in order to self- administer dopamine each time came in handy when I needed to see what I’d been doing.

For that matter, breaking things down by branch and by commit is just a really useful way of thinking about those sticky decisions I talked about earlier. Not only can you answer your own questions in multiple ways and see which one works best for you, but the simple act of considering what a branch should constitute and what a commit should constitute breaks the design decisions down into their constituent parts for easy mental digestion.

### Really, what I’m saying is, use git. It’s great. So, here’s how I use it after linking a remote and local repository together:

To see the git log, and its commit numbers and commit messages:

`git log`

Remember to scroll down the log with d, up with b, and quit with q. 

To checkout a specific commit:

`git checkout  commit-id`

To checkout a branch:

`git checkout branch-name`

To create a new brach:

`git checkout -b branch-name`

To stage for commit:

`git add file-name`

Or to add all files (including new, untracked ones):

`git add .`

To add a message and commit in one go:

`git commit -m “message here”`

To stage, add a message, and commit everything in one go (except untracked, new files):

`git commit -a -m “message here”`

To push your commits to the remote repository:

`git push origin branch-name`

To push your commits and actually create the remote branch in one go:

`git push -u origin branch-name`

To merge, first checkout the master branch, then:

`git merge branch-name`

To delete a finished branch (do this from master too) :

`git branch -d branch-name`

I’m not all that good at git, but even this much knowledge has been so helpful for me. Hopefully having written this, I’ll stop googling all of these basic commands for a while now. Even so, I encourage all gidiots everywhere to keep learning how to use this powerful tool.

