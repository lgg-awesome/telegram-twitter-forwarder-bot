# telegram-twitter-forwarder-bot
![logo](logo/logo.png)

Hello! This projects aims to make a [Telegram](https://telegram.org) bot that forwards [Twitter](https://twitter.com/) updates to people, groups, channels, or whatever Telegram comes up with!

You can check it on Telegram: [@TwitterForwarderBot](https://telegram.me/TwitterForwarderBot)

#### Credit where credit is due

This is based on former work:
- [python-telegram-bot](https://github.com/leandrotoledo/python-telegram-bot)
- [tweepy](https://github.com/tweepy/tweepy)
- [peewee](https://github.com/coleifer/peewee)
- [envparse](https://github.com/rconradharris/envparse)
- also, python, pip, the internets, and so on


So, big thanks to anyone who contributed on these projects! :D

#### How do I run this?

**The code is currently targeting Python 3.5**

1. clone this thing
2. fill secrets.env (see next readme section)
3. create your virtualenv, activate it, etc, e.g.:
    ```
    virtualenv -p python3 venv
    . venv/bin/activate
    . secrets.env
    ```
4. `pip install -r requirements.txt`
5. run it! `python main.py`

#### secrets.env?? u wot m8?

First, you'll need a Telegram Bot Token, you can get it via BotFather ([more info here](https://core.telegram.org/bots)).

Also, setting this up will need an Application-only authentication token from Twitter ([more info here](https://dev.twitter.com/oauth/application-only)). Optionally, you can provide a user access token and secret.

You can get this by creating a Twitter App [here](https://apps.twitter.com/).

Bear in mind that if you don't have added a mobile phone to your Twitter account you'll get this:

>You must add your mobile phone to your Twitter profile before creating an application. Please read https://support.twitter.com/articles/110250-adding-your-mobile-number-to-your-account-via-web for more information.

Get a consumer key, consumer secret, access token and access token secret (the latter two are optional), fill in your `secrets.env`, source it, and then run the bot!

#### Setting up cronjob

**Make sure crontab user have write access to venv directory**

I recommend to create a symlink for easy check if process is running
1. navigate to project folder
2. `ln -sT ./telegram-twitter-forwarder-bot.py ./main.py`
3. use run.sh script in cron:
`* * * * * cd /any/path/telegram-twitter-forwarder-bot && ./run.sh >> /dev/null 2>&1`
4. you can change time for checking to any you want
