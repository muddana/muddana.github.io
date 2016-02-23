---
layout: post
title:  "NFCalories : Hacking Eating Tracking"
date:   2015-09-20 22:45:37 -0500
categories: hackathon
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/UnSA2kIdjZ0" frameborder="0" allowfullscreen></iframe>

Problem : Tracking food consumption for users in a cafeteria setup. 

Recently there has been a significant rise of health tracking applications like Fitbit, Jawbone etc which track physical activities. However, there is no good solution to track food consumption.


Solution : We present a RFID based solution to solve the problem of food consumption in a cafeteria environment. 

The setup involves having RFID tags on each plate/container(think a salad bowl or a soup bowl or a pizza plate etc.) on which food is served. A smart serving station determines the food and amount of it in the container and associates the RFID tag of the container with the food being served in it. Hence we get the accurate amount of food being served in each container.

The user chooses and picks his food from various food stations according to his own choice. Say the user chooses a cup of soup and a sandwich bowl. When the user checks out food at the counter, our system reads the RFID tags and updates the database about the user food choice. Since RFID tags are very unobtrusive to read, and user would have a smooth checkout process. Also for the same reason, this system can work beside the usual cash-checkout-counters and be completely independent of it. 

Accurate food consumption is very desirable but not a necessary requirement. To determine this we propose a smart scale system which determines the plates being returned after the food consumption and weighing them before discarding. This would in various cases yield the food being wasted and perhaps more importantly the exact amount of food consumed by the user. 

Following is the flowchart of the 3 step process described above:

* Serve         : Associate a plate with the food & hence nutrition data
* Checkout      : Associate food selection with the user
* plate return  : Estimate food consumption/waste for each user.


<iframe src="https://docs.google.com/presentation/d/1qo04-XxruYGAeyVnumdJkPUnWMyyqehzOA76ynr-Tw8/embed?start=false&loop=false&delayms=3000" frameborder="0" width="960" height="749" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Hacker team &quot;NFCalorie&quot; on tracking people&#39;s eating behavior in a cafeteria setting <a href="http://t.co/xbMXlOdd9X">pic.twitter.com/xbMXlOdd9X</a></p>&mdash; Hack-Eating-Tracking (@HackEatTrack) <a href="https://twitter.com/HackEatTrack/status/645699007566622722">September 20, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>