---
layout: post
title:      "Final project: Tweetter app"
date:       2017-12-09 12:07:36 +0000
permalink:  final_project_tweetter_app
---


Created a light replica of the twitter app where users have tweets and comments, a tweet can have many comments and a comment can only belong to one tweet.

1. Implementation of the with a separate back end from the front end
2. Back end done with Rails configured as just an api server serving json data to various end point
3. Front end done with React
4. Demo of the app deployed on Heroku at: https://mytweetter.herokuapp.com

Specs implemented with the app:
* Manual authentication on server side with bcrypt gem
* Manual authentication between server and client through JWT
* Redux to manage the state shape of the app
* Redux Thunk to dispatch async actions
* ActiveModelSerializer to shape the data served at end points
* Normalizr to shape the data received by the client
* Optimistic update to enhance UX and reactivity of the app
* Semantic ui for UI
