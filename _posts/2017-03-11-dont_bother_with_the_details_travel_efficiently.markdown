---
layout: post
title:  "Don't bother with the details, Travel efficiently"
date:   2017-03-11 16:09:09 -0500
---


*So today, I am releasing the very first version of Travelx, a new social platform for people to share tips with their folks regarding travels. Rather than spending hours screening comments from strangers on larger website to find the right spot, hotel, coffee restaurant, you name it, when on vacations or visiting an unknown place, you can check if some of your friends have already been there and grab their tips.*

Don't get me wrong, this version is not even an alpha as definitely not ready to be released yet to the public but it is a gross preliminary draft of ... an app that can become ... big if it really solve people's issue. Despite, all the tools available to us, I still personally struggle when I am on vacations, or in some places I don't know, to find the right restaurant or coffee on the spot. May be because I am a bit picky but who is not? Either with food, or drink, or atmosphere, or music or whatever you focus on when you look for something, you generally want to be pleased with *"that particular thing you looking for".* And to be franc, in these moments, who wants to waste time reading hundreds of comments from strangers that you are not even sure whether they have the same standards of requirements in what you are looking for. Something that is supposed to be *"decent"* or *"awesome"* to you could end up totally different for someone else and vice versa. So, what could be best than asking people you know because it is easier for you to gauge their standards so when they will tell you whether they like something or not and this on a scale of 0 to 10, it is way easier to assess what they mean. But, hey!, who is gonna ask all his friends, parents, and relative if they have been where you plan to go and to write them the usual email with the best spot for coffees, site visits, lunches, pizzas, bars, cocktails, tapas, etc? Well basically no one. And who wants to write this email? No one either. It takes time and we are lazy. So travelx will try to solve these problems.

**So how does this first version work?**

This is a web app version based on ruby and ruby on rails. There is no front end done so far so I have to admit it is quite ugly and as a consequence the user experience is ... bad ... fine, it is awful ... but this was not the priority at such an early stage. What we are focusing on is a quick and easy app to use with a limited number of pages to navigate through. As a user, you can: 
* search through friends and add (or delete) friends
* check your friends activities and boards (which regroup several activities)
* pin your friends activities to bring these activities to your own list of activities
* organize your own activities within various boards
* create, edit and delete activties as well as boards

It doesn't seem a lot but being able to do that is already quite extensive while focusing only on the core function that you need. Later on, I will add additional functionalities that will deeply reinforce the social part of the app, and other that will make it not only user friendly but also more "polished" so to speak, and closer to a ready-to-be released version... so bear with me ;)

**Where to find this first version to go throught the code?**

Go to my github at https://github.com/ivanpilot/travelx

**A few technical points to be mentioned?**

hmm, I am not sure. You can go to my github portfolio and review the code directly. It should be self explanatory. I would just add that
* I implemented my own authentication system with the bcrypt gem
* I used Pundit to create an authorization system for different user type (user vs. admin)
* I used the Omniauth gem to allow a user to sign up and log in with his own Facebook credentials

**Copyright related to the project and this blog article**

Ivan Pilot ivanpilot@gmail.com Copyright - All rights reserved


