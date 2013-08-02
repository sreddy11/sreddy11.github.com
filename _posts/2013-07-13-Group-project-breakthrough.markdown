---
layout: post
title: "Group Project BreakThrough" 
date:   2013-07-03 06:44:13
---

A major feature of the RPS application is complete: 2 users can play one round.

The tricky part of this was to make the two players choice sync up. I was running into an issue before where each 
person's session would create a new round. Thus, the choices each player was making would map to a different 
round_id so a winner could not be determined. But I was able to work up a way to see if one player had already 
creaed a round and if so map the users choice to that round.

From here, we now have to play multiple rounds. This should be easy, since it will essentially be looping this
play round code until the match is over.

Intern out.
