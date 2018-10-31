---
layout: post
title:      "TFW every object wants to be #4"
date:       2018-10-31 17:03:02 +0000
permalink:  tfw_every_object_wants_to_be_4
---


For my Sinatra project, I decided to build a simple video game backlog tracker. I figured there are probably a lot of people out there like myself who buy games for myriad reasons despite already having a backlog of unplayed games. This would be my way to keep track of that list. 

In all of the labs throughout the Sinatra section, I’ve had the most difficulty with the patch actions.  I expected to spend a good amount of time debugging my edit form for this project (I was correct), so I decided to leave that one for last. Once I had the rest of the app working, I came back to the dreaded edit function. 

Building the form and controller actions weren’t super challenging since it was a pretty basic app, so the initial build went pretty quick. But debugging the issues that followed took more time than I’m willing to admit. 

The first issue was that after a user submitted the edit form, the game object became assigned to another user. This was caused by a simple typo that I caught pretty quick. The second issue was more complicated than the first, this one would change the database ID of an object to “4” after it had been edited. This would mean that the original object stayed as it was in your list, and the modified version would replace whatever used to be the 4th item in the database. 

I spent at least a couple hours trying to debug this one. I couldn’t find anything even similar online, I scoured every character in my code, made a hundred little tweaks here and there. In the end, the fix is always the most frustrating thing that should have been the most obvious first solution. In my controller, I was searching for the game in the database by calling `Game.find(params[:id])` and that clearly wasn’t working. The first edit I made in trying to fix this bug was to change that to `Game.find_by(“id” => params[:id])` but that didn’t change anything. It took me way too long to realize that `Game.find_by_id(params[:id])` was the right method to use here. And that was my magic fix.

I’m still not sure why it had decided that id 4 was the one to replace, but using the find_by_id method will be my first go to from now on. It turns out being specific is a good practice when it comes to ActiveRecord methods. 
