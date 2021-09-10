#Required package to work: praw, pyTelegramBotAPI
import os
import telebot
import praw
import random

API = 'your-telegram-api' #You can obatin this by talking with @BotFather

bot = telebot.TeleBot(API)

@bot.message_handler(commands=["yourcommand"]) #Change yourcommand with the command you want. Use this text when talking to bot. For example, this code will run if you write to your bot /yourcommand
def sendPhoto(message):
  #You can get client_id and client_secret by creating a new app on reddit: https://ssl.reddit.com/prefs/apps/. The redirect uri should be http://localhost:8080 if you don't plan to deploy the bot anywhere.
  r = praw.Reddit(
    client_id='client-id', 
    client_secret = 'client-secret', 
    user_agent='example'
    )
  post =  r.subreddit('yoursubreddit').random() #This will work only with subreddit that has the random function.
  if not post.is_self:
    bot.send_message(message.chat.id,post.url)  #Sending the url will send the image too.

bot.polling()
