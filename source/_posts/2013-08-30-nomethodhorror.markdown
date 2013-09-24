---
layout: post
title: "NoMethodHorror"
date: 2013-08-30 17:36
comments: true
categories: [tutorial, rails, learning, NoMethodError] 
---


In my app I want to accept a pending friend request. But when I hit the "accept" button I get a NoMethodError in UserFriendship#edit: <code>undefined method `requested?' for nil:NilClass</code>. 

views => user_friendship => edit.html.erb: 
<pre><code><% if @user_friendship.requested? %>
  Do you really want to be friends with <%= @friend.first_name %>?
<% end %>

<% if @user_friendship.accepted? %>
  You are now friends with <%= @friend.first_name %>s
<% end %> 
</code></pre>

I still haven't figured out why <code>@user_friendship</code> returns nil. 
But I read a bit about NoMethodErrors and I found this to be a cute descriptive
example: 

  > So, you press the button on the forehead of the first person and the person says, "Julian McNeil." Ok good. Then you press the button on the forehead of the second person and the person says, "Sally Reynolds." Good again. When you get to the 3rd person, there is no person. Just a button on the floor that says full name. You press the button anyways. Nothing. How can that person say their full name if there is no person? That 3rd person is nil. [-Source](https://teamtreehouse.com/forum/help-i-keep-getting-undefined-method-fullname-for-nilnilclass?sort=newest&amp;topic=Ruby)

Then I ended up reading a bit about the method [try()](http://www.ruby-on-rails-outsourcing.com/articles/2010/03/03/using-try-method/). If I do <code>@user_friendship.try(:requested?)</code> I can "escape" that NoMethodError. It´s not going to solve my problem but at least I got my tests to pass for a moment ;). 


<img width="620" src="https://monosnap.com/image/sOOgbAv1r7R9IdRa6BhH4uDh9.png" alt="gandalf" title="you shall pass">
