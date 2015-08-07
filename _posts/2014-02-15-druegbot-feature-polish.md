---
layout: post
title: Finishing up a few more features
---

More features in the bag
===
Today I managed to wrap up what I considered to be a few of the missing features.  I wanted to lock down the specifics on how the bot would know which user to run as and log in as if someone wanted to us that option.

<!--more-->

I also hadn't gotten the tab switch mechanism down correctly for moving between the Main, Collection and Trade tabs.  Since the trade tab needs to be opened to post the trade messages and the collection scene needs to be opened to bot get a users current collection and make cards tradable as they are purchased I thought this was an important feature.  Fortunately it all feel into place very nicely and now I'm only trying to figure out a way to programatically show all versions of the cards on the collection screen.  I'm not sure why the default is to have it stack the same versions but it is a bummer.

So following along with the break through I made with the above features.  I wanted to be able to add cards and tickets to be trade-able after completing trades.  So I needed to be able to do this consistently and quickly and ensure that I am adding to the active trade binder.  This also all fell together very nicely and I am now able to add cards and tickets as trade-able after a successful trade, it takes into account the bot settings for max trade-able for all items except tickets and booster packs.  If its requested enough I'll add the settings in to limit the number of these that will be marked trade-able as well but it seems odd to do that if you are going to buy and sell these items.

To keep track of this information I had to modify the database a little but it was work that needed to be there.

Logging
---

I also took some time to add trace logging to almost every method in the code to ensure that if errors were encountered that caused the program to close I can track down which area and hopefully which line is the offending piece of code.

I do not and will never log password information since I feel very strongly in respecting property.  Which is why although there is an option to have the bot log in for you it works just fine if you are already logged in when you run the code.  However, when I get the restart functionally implemented that will only work if the user is willing to put their password in the execution file.

Upcoming
---
I've gotten the functionality incorporated to initiate trades between buddy list users.  So I need to get the functionality for adding buddies and then write the transfer logic for moving cards between two bots in the same trade group so that I can do collection smoothing (the act of trying to keep a set number of cards in all your bots based on bot priority).

I want to get the functionality for starting the MTGO client from the bot itself.  Then build on that to handle MTGO client crashes so that I can do a restart whenever necessary.

The website for creating your Bot Grouping and adding individual Bots.  Then modifying the settings for each individual bot.  I'll leave the functionality for setting individual card prices for last since I'm not sure how I want that UI to look yet.