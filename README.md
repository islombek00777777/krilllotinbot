# krilllotinbot
#hello  there,i have created my first bot ,check it i hope you can use widely!!!
#@Cyrlltn_bot
from transliterate import to_cyrillic,to_latin
import telebot
TOKEN='7355457091:AAEWR_NyivAJ5c_Cvo99uDM3KgN_wqmHv28'
bot=telebot.TeleBot(TOKEN,parse_mode=None)
@bot.message_handler(commands=['start'])
def send_welcome(message):
    javob="Assalomu aleykum ,ISLOMBEK tomonidan yaratilgan botga xush kelibsiz: "
    javob+="\tmatn kiritng"
    bot.reply_to(message,javob )
@bot.message_handler(func=lambda message:True)
def echo_all(message):
    msg=message.text
    if msg.isascii():
        javob=to_cyrillic(msg)
    else:
        javob=to_latin(msg)
    bot.reply_to(message,javob)
bot.polling()    


