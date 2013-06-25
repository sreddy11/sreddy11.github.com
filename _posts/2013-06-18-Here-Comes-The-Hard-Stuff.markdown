---
layout: post
title:  "Here comes the hard stuff"
date:   2013-06-18 11:16:50
---

Today, I started working on the replying to comments feature of HackerNews. I remember in my Intro CS class when we learned about recursion,
and saying to myself "I will probably never have to use this in actual programming". But come to find out, that is far from the opposite.
With this feature, the very nature of it is is built around recursion, in that people can reply on comments on comments on comments. 

Recursion really helped in the views when I was trying to create and indent for each comment reply on a comment. I ended up using recursive 
list in the view, which I was surprised worked as well as it didi, considering I was just playing around with the HTML and magically made
it work. Sometimes it is better to be lucky than good.

{% highlight ruby %}
<% comments.recent.each do |comment| %>
  <ul>
    <%= render("comments/comment", :comment => comment) %>
      <% if comment.has_comments? %>
          <ul>
            <%= render("comments/comments", :comments => comment.comments) %>
          </ul>
      <% end %>
    </ul>
  <% end %>
{% endhighlight %}

Intern out.

