---
layout: post
title: Bots kept running during my entire vacation
---

When I left for vacation I wasn't sure my bots would stay online and keep doing work especially during two separate update days.  But everything seemed to have worked pretty well.  They made a reasonable number of completed trades (reasonable being relative).  I did have one person manage to find a little loop hole in my pricing so they got a few extra tickets for a card that was being bought for about twice its price.  Oh well these things happen and their exploitation helped me figure out what I had done wrong and fix my auto update pricing code.

<!--more-->

I added a few more features to the actual bot site.  It now has an api to retrieve my buy and sell prices that I use for each card so someone else can take this and use it or they can just use it to look up card prices until I finish making a more friendly UI.  The api is mainly for use with other people's bots if they want another price point of reference so they don't have to try and figure out how to scrape the prices from my sales pages (which don't exist yet).  I've also included a collection price checker that will let you know how much your collection is worth.  Its not very robust yet it only takes in a csv file in a very specific column layout.  But its a start and maybe someone will appreciate it.  I use it to determine if ebay lots are a worthwhile deal.  Right now the ebay sales are selling for only a few dollars less than my quote so not really a good deal.  I think when I get a chance after my first task this afternoon I will work to accept deck files instead of just csv since this is the method that I prefer to use when I'm exporting.

Today I think I'm going to finish up the post code that will rotate through the standard cards that are worth some money so maybe I can get some people to sell me specific cards that I am looking for as they rotate.   I suppose I'll have to add a bot setting similar to the Set filter that filters on which cards to show on the classifieds board.   I'm planning on showing the buy and sell price of each card with the buy or sell price marked out with a dash if I am not buying or selling the card.  Hopefully that will be self explanatory and will work out the way I want.  I think I'll have the cards on the board rotate every two minutes so that it is somewhat fresh.

After I finish these little tweaks I'll probably get to work on the automated tests I am lacking.