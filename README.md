# Slack Apps

## What does a Slack App Do?
Slack Apps allow developers to create additional functionality to their (or any) Slack teams. The apps can do this in a number of ways including providing more information, organizing that information in helpful ways, providing the opportunity to interact with another system (like a CMS), and more.

There are two types of Slack apps that are built in similar ways.

The first is internal apps which are not published on the Slack App Store but rather live only on your team. These apps might include sensitive company information or access or may be so niche, other teams wouldn't need them.

The other type of app is distributed apps. These apps are meant to be published and shared with the world so that they can be installed and used in any Slack team. Make sure these apps don't include any access to your personal company systems or else you could be hacked (if it even makes it past the Slack app reviewers). Because these apps are public they have to go through an extra step of approval by Slack.

## Slack App Examples

You can find the [list of all public apps](https://slack.com/apps/) on the Slack website.

Here are some examples and other listicles of cool Slack apps curated by our team:
- [15 of the Best Slack Apps, Integrations & Bots to Try](https://blog.hubspot.com/marketing/slack-apps-integrations)
- [14 Best Automated Bots You Need for Your Slack Channel](https://www.makeuseof.com/tag/14-best-automated-bots-you-need-for-your-slack-channel/)
- [12 Slack Bots to Superpower Your Team](https://blog.statsbot.co/12-slack-bots-to-superpower-your-team-e022a9692174)
- [Glossary Bot](https://github.com/codeforamerica/glossary-bot)
- [Quackbot](http://www.niemanlab.org/2017/10/if-it-looks-like-a-duck-swims-like-a-duck-and-quacks-like-a-duck-then-its-probably-a-slack-bot-for-journalists/)

## API Libraries

You can find lots of information about making and using Slack Apps on their [official documentation website](https://api.slack.com/).

But depending on which programming language you're using, it's recommended you use one of their many client libraries. Here's a list of some (these libraries were built and maintained by Slack):
- [Python](https://github.com/slackapi/python-slackclient)
- [Node](https://github.com/slackapi/node-slack-sdk)

You can also find great tutorials and base examples for common tasks on the [Slack Github page](https://github.com/slackapi).

## Setting Up Your Slack App

Once you have your programming language of choice and your project set up you'll quickly notice you need an API key. To get one you'll need to have access to a Slack team of your own. Once you sign in on `yourdomain.slack.com` website you can make a new app by going to [this link](https://api.slack.com/apps?new_app=1). For help making a new app you can check out the official documentation [page for this](https://api.slack.com/slack-apps#creating_apps).

You'll need to set up the correct permission scopes and other capabilities of your app AND install it on your team (yes it needs to be installed even if you choose the team as the `Development Workspace`) before you can get an API Token.

Once your app is set up you can get your API tokens in the `OAuth & Permissions` section of your app admin.

Then you can create the proper API object with the following code:

### Python

```python
from slackclient import SlackClient
token = [YOUR_API_TOKEN] // Remember to keep all sensitive information away from Github like this key

slack = SlackClient(token)
```

### Node

```javascript
import SlackAPI from '@slack/client'
const token = [YOUR_API_TOKEN] // Remember to keep all sensitive information away from Github like this key

const slack = new SlackAPI(token);
```

## Slack App Capabilities

### Having Your App Talk to Slack

#### Basic Messages

The easiest way to make your app do anything is to give it a bot user. Bot users are used to talk to members of your Slack team through code. If you have it setup properly you can post messages easily using the postMessage function on your API object.

```python
slack.api_call(
  "chat.postMessage",
  channel=channel_Id,
  text="Hello World!",
)
```

### Node

```javascript
slack.chat.postMessage(channelId, 'Hello World!')
```

For help posting messages you can check out the official documentation [page for this](https://api.slack.com/docs/messages).

#### More Complex Messages

Slack apps have the capability to format messages in much cleaner ways than human users can by leveraging the power of attachments. These attachments can be images, links, other text, or even interactive components (see next section).

Let's take a look at what one of these messages look like.

![Complex Messages](https://a.slack-edge.com/bfaba/img/api/messages-full-featured.png)

And now let's take a look at the code for this message:
```javascript
{
    "text": "New comic book alert!",
    "attachments": [
        {
            "title": "The Further Adventures of Slackbot",
            "fields": [
                {
                    "title": "Volume",
                    "value": "1",
                    "short": true
                },
                {
                    "title": "Issue",
                    "value": "3",
            "short": true
                }
            ],
            "author_name": "Stanford S. Strickland",
            "author_icon": "http://a.slack-edge.com/7f18https://a.slack-edge.com/bfaba/img/api/homepage_custom_integrations-2x.png",
            "image_url": "http://i.imgur.com/OJkaVOI.jpg?1"
        },
        {
            "title": "Synopsis",
            "text": "After @episod pushed exciting changes to a devious new branch back in Issue 1, Slackbot notifies @don about an unexpected deploy..."
        },
        {
            "fallback": "Would you recommend it to customers?",
            "title": "Would you recommend it to customers?",
            "callback_id": "comic_1234_xyz",
            "color": "#3AA3E3",
            "attachment_type": "default",
            "actions": [
                {
                    "name": "recommend",
                    "text": "Recommend",
                    "type": "button",
                    "value": "recommend"
                },
                {
                    "name": "no",
                    "text": "No",
                    "type": "button",
                    "value": "bad"
                }
            ]
        }
    ]
}
```

The first thing to notice is that the image above has four sections (divided by the gray lines to the left of each section). There are also four objects in attachments. That's not a coincidence.

There's a lot that goes into building these kinds of messages and the Slack documentation explains it best. For help with message attachments you can check out the official documentation [page for this](https://api.slack.com/docs/message-attachments). You can also test your attachments with their [message builder](https://api.slack.com/docs/messages/builder).


### Having Slack Talk To Your App

In order to allow Slack to talk to your app, you'll need to build webhooks (also known as a REST API) into your app. You can watch [this video](https://www.youtube.com/watch?v=7YcW25PHnAA) for a good explanation of what a REST API is and check out [this gist](https://gist.github.com/brizandrew/e5ff878f8e3c17386de037c201386dc1) to see an example of a simple Flask app with webhooks.

When you're developing your app, you'll likely have your webhook at a localhost web address which won't work for Slack. Luckily, you can use [ngrok](https://ngrok.com/) to create a "tunnel" from a public link to your localhost.

#### Interactive Components

As I said in the last section, you can also include interactive buttons as attachments. To set up your app to receive these interactions you'll have to enable them in your app dashboard under `Interactive Components`. With a URL to an appropriate webhook link (remember it has to be public and HTTPS compatible).

Once you've done that, any button pressed on any message created by your app will send a POST request to that link. You can differentiate between different actions by using the `callback_id` in your attachment.

For help with interactive message components you can check out the official documentation [page for this](https://api.slack.com/interactive-messages).

#### Event Subscriptions

You can also have your app "listen" for certain things in Slack such as `a channel was created` or `a message was posted in a channel`. For a full list of these you can look at [this page](https://api.slack.com/events/api) in the documentation. To setup your app to receive these events you'll have to enable them in your app dashboard under `Event Subscriptions`. From there you can choose the events you want your app to subscribe to and provide a webhook link.

For help with events you can check out the official documentation [page for this](https://api.slack.com/events-api).


#### Slash Commands

A final way to have Slack talk to your app is through user slash commands. Essentially this lets users call your app and provide it information. Think of it as letting Slack users call specific functions in your app. The syntax for using a Slash command in Slack is:

```
/name-of-command some text as an argument
```

Notice that the name of your command has to be a single word, and every word after that will be passed as an argument to your webhook link.

So you have to set that up first by (you guessed it) going to your app dashboard and going to the `Slash Commands` tab. From there you can give your command a name, and even give each one their own webhook URL.

For help with slash commands you can check out the official documentation [page for this](https://api.slack.com/slash-commands).

## A Note On Tutorials

Unlike many other API documentation, Slack's API documentation does a fantastic job explaining each part of their API filled with tutorials and examples of their own in an intuitively organized website. I highly recommend you use that as your tutorial of choice.

## Tutorials From Around The Web

With that being said, however, here are some tutorials from around the web curated by the team:
- [A beginner’s guide to your first bot](https://slackhq.com/a-beginner-s-guide-to-your-first-bot-97e5b0b7843d)
- [How To Write a Slack Bot — with Python Code Examples](https://medium.com/@julianmartinez/how-to-write-a-slack-bot-with-python-code-examples-4ed354407b98)
- [How to Deploy Your Slack Bots to Heroku](https://blog.heroku.com/how-to-deploy-your-slack-bots-to-heroku)
- [Building PokéSlacker: A Slack Bot Tutorial](https://blog.insightdatascience.com/building-pok%C3%A9slacker-a-slack-bot-tutorial-c1bc041591bb)

## Other Interesting Readings
- [How publishers are using Slack bots internally and externally](https://digiday.com/uk/article-performance-serving-ads-publishers-using-slack-bots/): A window into how news organizations like Buzzfeed and The New York Times use Slack bots to accomplish tasks around the newsroom.
-

## Credits

This post was written by [Andrew Briz](https://github.com/brizandrew) with sources and links provided by [Mary-Lou Watkinson](https://github.com/orgs/weimer-coders/people/M-Watkinson), [Gabrielle Calise](https://github.com/orgs/weimer-coders/people/gabriellecalise), [Ryan Serpico](https://github.com/orgs/weimer-coders/people/zuckerco), [Nicole Dan](https://github.com/orgs/weimer-coders/people/nicoledan), and [Caitlin Ostroff](https://github.com/orgs/weimer-coders/people/ceostroff)
