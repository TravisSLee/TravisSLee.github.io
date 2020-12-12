---
layout: post
title:      "My Rails Project"
date:       2020-12-12 14:54:23 -0500
permalink:  my_rails_project
---


I got to say this project was more difficult than expecting due to the fact I took this project too lightly, that my troubleshooting skills need to improve, and that my nowledge of RESTful routing needs to improve. I kept on making syntax errors that I couldn't catch. I will learn from these mistakes to make myself a better programmer.

The first step on took on these project was booting up "rails new", which booted up a rails framework that I needed to start this project.  Next, I used Devise to create a simple User model with full signin, signup, and login capabilities. After, that I implemented a third party signin/signup with Github OmniAuth. 

The next step of the project was plan the other two classes that I needed for my project. I chose athletes and memorabilia because I am a big NYC sports guy. For these two models, I used "rails g" to generate the MVC for both these classes. I started to run into trouble when I got into pathing, because they're very peticular on what I pass through them. From what I've learned from my instructor, Nancy, the new_resource_path doesn't need an object passed through it. The new_nested_resource_path and edit_nested_resource_pathneeds both parent and child objects passed throught it. And finally for some odd reason my delete functions need a button, then my delete a nested_resource_path needs the id's of both parent and child resource passed through in order to delete the child resource. And what I tripped me up on my new form was the select_tag. All it took to fix it was to comment out that it accepts_nested_attributes in my Memorabilia model.

Thanks to all that helped me with my project!
