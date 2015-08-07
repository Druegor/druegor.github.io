---
layout: post
title: MTGO Trade Bot Beta release almost ready
---

Lots of new features added and existing bugs resolved
===
So I'm not quite sure where I left off before I left for Mexico and what I've gotten done since I got back.  But I've added some key new features for sure.

<!--more-->

  - Now when the executable for the bot is started it will start up the MTGO beta client getting the newest version and then log in when the screen becomes available.
  - On initial start-up of the bot it will update the collection cards / trade able cards based on your bot settings.  This is in case you decided to use your account and do some trading or managing of cards on your own.  That way the database will properly reflect the cards that your group has and which account has those cards, etc.
  - The chat window is still causing some issues since I have been using the chat window to send messages by actually clicking the button which was not always enabled since apparently I type in the text box and try to click too fast.  It's been a pain to figure out when the button is enabled but I believe I have resolved this issue by slowing some things down.
  - I was able to find a few more online price points for initial card pricing of all types.  So now I can have my bots sell/buy commons and uncommons at their appropriate values.  It will also allow me to have more focused bulk buying bots.
      - This is because when you run a bulk bot the point is to get some increased value from the whole bulk purchase.  So my bots run on the idea that if buying the card individually would cost the same or more than the bulk price I'm offering then I'll purchase it.  Otherwise its more cost effective to find it elsewhere.
      - This is also why my bots will progressively take more and more copies of a given card.  My bots that buy the most expensive cards will take the least number of copies 6-8.  Where the bots that buy cards buy the hundreds will usually take about 4 per bot I'm running.

Remaining Bot Features
---
There are still a few features for the bot itself that I want to finish before I would want to consider it ready to progress from beta.

  - I want to get some automated tests for the core functional logic.
  - I need to switch the logging from local file logging to instead store the logs in a queue and push them to the server using the API when the queue fills up or an error is encountered.
  - I want to get the logic implemented to do the automated transfer of cards between two bots so you can move play sets up to each of your bots in order.  I think this shouldn't be too hard it just didn't seem like as important of a priority for initial release.
  - Currently if you lose internet connection or the application disconnects you that is pretty much it.  There is no good way implemented to handle internet connection loss, disconnection or most importantly the program shutting down from an error.
  - The last is just the automation of the agreement to the Terms and Conditions screen when the software as had an update.  This should be simple but I'll have to wait until the next time I see the screen before I can code for it.

Bot Website
---
The site is slowly coming together.  I just added the feature to sign up for an account but I haven't yet implemented the ability to add groups or bots to groups yet.  I'm working on the functionality to edit the bots current running settings first.  Since having the ability to add the name of your bot to my server seemed like a bit of a waste if you couldn't even see what the available settings are for the bot.

I'm about done with the settings edit screen I'm just trying to make it a little cleaner by separating it into tabs.  After that I'm going to add a brief counter to the page that lets you know when you can expect the bot settings to go live on your current running bot.  This won't be seen by anyone but me currently since I'm the only one with running bots.  But the update timer for changes happens every 10 minutes.  So it will be a timer based on how much time has elapsed since the bot was last updated from the server.

The bot updates from the server so frequently to make sure that each bot knows how many copies of any given card the entire group has as a whole.  This way the max copies to buy setting actually means something.  This value can be different for each bot so if you have one that buys rares at a dollar a piece and you only want to get 4 of any card on that bot that is fine.  Your other bot that buys at 50 cents can be set to buy 8 so that a customer can sell their cards for prime value to one but still offload them to another bot when you've met your quota if they want.

When I finish the bot settings feature I'm going to open up the ability to add a group and your bots to that group.  This will allow people to start providing feedback on the settings page and the customized message page when I finish that.  Also they can get everything set-up and ready to go for when I release the live product.

I'm still fudging with the numbers one how I would like to fiscally get reimbursed for the bot.  I am currently working off the idea of a flat 2% across the board for the initial release with some sort of incentive program for each month.  Maybe a few trades free based on the amount paid the month before, similar to a cash back program.  I think for the first month of two I'll provide free use to anyone that wants to try it out since essentially everyone that uses it right away is going to be part of my beta program.  We all know that beta programs should be free.  No point in paying for a product that only works some of the time.
