---
layout: post
title:  "Weekend Hack : BlackJack & BusFind this week"
date:   2010-03-22 14:41:00 -0500
categories: hack
---

I spent about 12 hours to finish an implementation of blackjack, mainly to design a library for card games. Writing blackjack using the classes helped me to refine the design from an earlier version. Wrote a server class(it doesn't have any networking capabilities right now). Here is the design in rails style(ofcourse the code is in c++ but here just highlighting the design)

{% highlight ruby %}

# NOTE: This is not actually ruby code. Using Active Record style relationships to communicate the architecture.

class Card
end

class Player
 has_many :cards
end

class CardGame
  has_many :cards #actually decks of cards
  has_many :players
end

# Blackjack implementation : talks on server channel to communicate with clients, right now no real communication just writing onto console
class BJPlayer <Player
end
class BJDealer < BJPlayer
end

# Games communicate with server channel which is assigned to each game by the server while initiating the game

class ServerChannel
end

class BlackJack < CardGame
   has_many :cards #stack of cards actually
   has_one :bjdealer
   has_one :server_channel
   has_many :bjplayers
end

class Server
 can_hold_many :card_games
end

{% endhighlight %}

Lot more to do, have to refine the code and try adding some networking capabilities to connect form real clients, but find the code here: http://github.com/muddana/blackjack

Also, last week was a better week for BusFind got 89 calls in total last week. see the picture below. So the number has increased from past week.thats a positive sign. I have got to work on putting up pamphlets to publicize BusFind around school sometime soon so that more people will get to know about BusFind. Also if i haven't mentioned already i have fixed one of the errors in BusFind which was causing some exceptions.

happy hacking.

![Bus Find Calls](/assets/7502307-03222010.png "busfind_calls")