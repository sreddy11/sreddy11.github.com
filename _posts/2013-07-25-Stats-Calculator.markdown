---
layout: post
title:  "Stats Calculator"
date:   2013-07-25 2:16:50
---

Today I worked on setting up a statistics calculator for the RPS app today. Chris showed me some cool ways to 
refactor my work by moving the code into a "StatsCalculator" class that lives in the lib folder. Furthermore, 
we found out some cool array methods for calculating streaks

My original code was just calculating streaks by looping through an array and keeping track of consecutive instances
in an array. But afterward, Chris, Zach, and I stumbled across a method called chunk that takes in a search
element and returns all consecutive instances that element in an array. So:

[1,2,2,3,2,2,2,4].chunk{ |x| x== 2 || nil).to_a => [ ["true,[2,2]], ["true", [2,2,2]] ]

Thus my code for calculating a longest streak looks like:

{% highlight ruby linenos %}

def longest_streak_for(arr, element)
    streak = arr.chunk{ |x| x == element || nil }.to_a.map { |k,v| v.count}.max
    if streak.nil? then 0 else streak end
end

{% endhighlight %}

Hope you learned something. Intern out.
