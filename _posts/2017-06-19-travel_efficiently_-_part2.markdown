---
layout: post
title:  "Travel efficiently - part2"
date:   2017-06-19 21:37:37 +0000
---


*Today, I am releasing the second version of this project with is purely to assemble new knowledge and try things.

As a reminder, the idea is for people to share tips with their folks regarding travels. Rather than spending hours screening comments from strangers on larger website to find the right spot, hotel, coffee restaurant, you name it, when on vacations or visiting an unknown place, you can check if some of your friends have already been there and grab their tips. Hopefully this will save you time!*

# The improvements
The previous version was a pure ruby and rails project without any js, css or anything improving the user experience. This time, it was all about adding some js and using jQuery and Ajax so, even though the design and css is still not there, the user experience is already much better.

1. Creating boards

When you create a board, you now have the possibility to create associated activities to that board and you can have as many activities as you wish. This is simply done with a bit of javascript, allowing me to add a activity field (description and rating) to the DOM each time the user click on the 'add activity' button

Then the creation of the board per se is done via Ajax, allowing me to display the new board title on the index view, as well as a full description of the newly created board and its related activities if any, and all of that without reloading/ refreshing the page 

2. Visiting boards

If you visit a specific board, you will still be able to see the actual board and its associated activities if any and you will still be able, provided that you have the appropriate right (owner or admin) to create, edit and delete the board and its activities. But the new thing is when it comes to navigate through your boards or through your friends' boards. Now, from a board show view, you will have access to 'next' and 'previous' buttons allowing you via jQuery and Ajax to navigate super easily through the boards and without reloading pages. Pretty awesome, right?

3. Authorization

Even in the first version of this project, I use Pundit in order to implement authorization based on the granted right of user. Given that we now use jQuery and Ajax to display boards and their related activities, the authorization from Pundit that happen in the controllers can't be used with javascript becasue the environment or the stack to be more precise is not the same anymore. So as we are using Active Model Serializer to obtain a json and serialize the ajax response, we wrote some instance method inside the Board serializer and the Activity serializer to test if a user's rights on some specific object and to implement authorizations even with javascript.  

Cheers,
Ivan


