# Slack Apps

Some information on making Slack apps. Some things to maybe look into:
- Webhooks
- Interactive messages
- Slash commands
- Bot messages

Help with [Markdown](https://guides.github.com/features/mastering-markdown/).

## Research



### Ryan

#### Tools and Documentation

* [python-slackclient | GitHub](https://github.com/slackapi/python-slackclient): As the name suggests this is a python client that allow you to make Slack bots and apps (slaps?) with Slack’s API. There are several other python clients, but this one comes from Slack itself. 
* [Slack API Documentation | Slack](https://api.slack.com/): Slack’s documentation for their API.
* [Building Slack apps | Slack](https://api.slack.com/slack-apps): This guide from Slack is light on code but goes in depth into the process of actually setting up a Slack app that can be used by others. They also have a whole page dedicated to [best practices](https://api.slack.com/best-practices) when making Slack apps. 

#### Tutorials and Examples

* [How To Write a Slack Bot — with Python Code Examples | Julian Martinez](https://medium.com/@julianmartinez/how-to-write-a-slack-bot-with-python-code-examples-4ed354407b98): This tutorial walks you through the process of setting up a Slack bot using Python. 
* [How to Deploy Your Slack Bots to Heroku | Heroku](https://blog.heroku.com/how-to-deploy-your-slack-bots-to-heroku): This is tutorial from Heroku walks you through deploying a Slack bot to Heroku. The process is familiar to anyone who deployed their Twitter bots to Heroku.

### Caitlin
In order to make a Slack App or Bot, you need to register for a user_id and an access_token. This [article](https://www.viget.com/articles/how-to-build-your-own-slack-app-and-bot/) explains it really well. In terms of explaining a sample python script, [this](https://www.fullstackpython.com/blog/build-first-slack-bot-python.html) isn't the clearest explanation, but it's good sample code to mess with.
Wait, giant list of walk-throughs for Python, Node and Ruby. [Link](https://botwiki.org/tutorials/slackbots/).

### Gaby


**Tutorial:** 

 - [Beginner’s guide to your first bot](https://slackhq.com/a-beginner-s-guide-to-your-first-bot-97e5b0b7843d)
This post includes different tutorials for creating your own Slack Bot. It also links to some interesting bots that people have already made, from bots that track the availability of the office toilet to a bot that schedules air quality reports. 


**Applying Slack Bots to journalism/ communications:**
 - [Journalism Bots: A Quick History and Ideas for Use in Your Newsroom](https://gijn.org/2017/12/11/journalism-bots-a-quick-history-and-ideas-for-use-in-your-newsroom/)
How can investigative reporters and newsrooms use Slack bots? Look no further than this article! This talks about bots in more general terms, from Facebook chatbots to Twitter bots, but it still is a good source of specific examples of how reporters have used bots successfully and could be a place to draw inspiration from. 

 -  [How publishers are using Slack bots internally and externally](https://digiday.com/uk/article-performance-serving-ads-publishers-using-slack-bots/) 
 This article discusses how news organizations like Buzzfeed and The New York Times use Slack bots to accomplish tasks around the newsroom. For example, Buzzfeed’s bot sends a notification to editors around the world when a story is doing exceptionally well so that they can decide whether or not to translate the content into another language. The New York Times has Blossom, a Slack bot that is able to predict an article’s success on social media. The Wall Street Journal and The Economist also use Slack bots to help with editorial workflow. 

 - [Slack bots have the keys to your processes. What could go wrong? Well...](https://www.theregister.co.uk/2018/02/28/devops_and_bots_achilles_heel_of_collaborative_software_development/)
This article discusses the pros and cons of bots, outlining potential pitfalls to avoid. 

 - [The Politics of Bots in Politics](https://medium.com/journalism-innovation/the-politics-of-bots-in-politics-a2e1486f9d94)
This article discusses how journalists used Slack bots during elections and other political events to achieve different tasks. 


**Examples of cool Slack Bots**

 - [Glossary Bot](https://github.com/codeforamerica/glossary-bot)
Glossary Bot is a Flask app that was built to run on Heroku. It lets users create their own glossary of terms and definitions, and the Github repository is documented very well. 

 - [Quackbot by Quartz](http://www.niemanlab.org/2017/10/if-it-looks-like-a-duck-swims-like-a-duck-and-quacks-like-a-duck-then-its-probably-a-slack-bot-for-journalists/) 
Quartz has its own BOT STUDIO which is pretty cool. One of the Slack bots this project has produced is Quack Bot, which has several helpful tools for journalists who program. (Also, here is a [news release on Quackbot](https://bots.qz.com/1455/announcing-quackbot-a-slack-bot-for-journalists-from-quartz-and-documentcloud/) and here is [more info on Quartz’s Bot Studio.](http://www.niemanlab.org/2016/11/quartz-launches-its-bot-studio-with-a-quarter-million-from-knight-and-plans-for-slack-and-amazon-echo/) ) 


### Mary-Lou
[Building Slack apps from Slack](https://api.slack.com/slack-apps)

* Here is Slack’s overview for building Slack apps. I think it is useful because it is Slack itself explaining Slack apps to you.

[App directory](https://slack.com/apps/category/At0EFWTR6D-featured)

* Here is the Slack app directory, which can be useful for us when we consider what kind of app we want to create so that way it is a new, fresh idea that someone hasn’t already created.

[App examples](https://blog.hubspot.com/marketing/slack-apps-integrations)

* This blog post gives examples of 15 different Slack apps, and I think it offers a wide variety for what we can do. Some are outright helpful for a newsroom, such as pooling together people’s contacts, and some are more fun, such as adding the gifs to conversations. So I think this gives a good, general overview of some ideas we might have. 

[Slack bots](https://zapier.com/blog/how-to-build-chat-bot/)

* This article is nice because it not only discusses how to build a Slack bot, but it discusses what a bot is (although we probably already understand that) and what types of bots you can make. So it gives us an overview of every part of the process we need. 


### Nicole
[14 Best Automated Slack Bots for Your Slack Channel](https://www.makeuseof.com/tag/14-best-automated-bots-you-need-for-your-slack-channel/)

* This gives some good ideas for responsive bots and tells you what's already out there.

[12 Slack Bots to Superpower Your Team](https://blog.statsbot.co/12-slack-bots-to-superpower-your-team-e022a9692174)

* This article gives some good examples of bots to boost productivity.

[Slack App or Bot User Integration](https://tutorials.botsfloor.com/slack-app-or-bot-user-integration-842c3843eea8)

* This is a review of what we went over in class that goes over the difference between an app and a bot.

[Building PokeSlacker: A Slack Bot Tutorial](https://blog.insightdatascience.com/building-pok%C3%A9slacker-a-slack-bot-tutorial-c1bc041591bb)

* For anyone who wants to use an API with their Slack app/bot
