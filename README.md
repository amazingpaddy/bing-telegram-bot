This is a telegram bot which uses EdgeGPT to post queries and get the response. **This bot cannot be shared publicly since its uses your browser cookies to authenticate you as bing needs you to be logged in**. So you should have your own bot using own browser cookie. 

Credit goes to the developers of [EdgeGPT](https://github.com/acheong08/EdgeGPT), who ingeniously reverse-engineered Bing Chat using browser cookies.

## Prerequisites:
* Accessible to Bing chat (If you are in waiting list, this bot may not work)
* Telegram App (latest version)
* Python 3.11
* Any IDE - VSCODE or PyCharm (Optional)
* Edge browser - As of now bing chat only works in Edge browser. But there are extensions available to enable the chat in other browser as well.

## What is working and not working
* No limits in how many requests you send. You can chat with bing as long as you want.
* option to choose to get response with or without reference links.
* **bot cannot remember the previous conversations, so you may not get proper response for the follow up questions.**
* if you get `IndexOutofBoundException`, restart your python script. If is still not working, export the cookies again and update the cookie.json file.

## Steps to have your own bing chatbot.

### step 1:

Clone or download this code to a any directory.

**`git clone https://github.com/amazingpaddy/chatgpt-telegram-bot.git`**

### step 2:
install EdgeGPT package

**`python3 -m pip install EdgeGPT --upgrade`**
**`pip install pyTelegramBotAPI`**
### step 3:
install [Cookie Editor](https://chrome.google.com/webstore/detail/cookie-editor/hlkenndednhfkekhgcdicdfddnkalmdm) extension in Edge browser.

### step 4:
Navigate to the Bing Chat webpage where you can post queries and receive responses. 

***Ensure that you have not reached the chat limit***, then export your cookie using the **Cookie Editor** extension. 

The cookie JSON string will be copied to your clipboard. **Save the cookie JSON in a file, for example, "cookie.json".** Ideally, save the "cookie.json" file in the same directory where you cloned the code.

### step 5:
Follow this blog - _**[How to Generate a Token for Telegram Bot API](https://medium.com/geekculture/generate-telegram-token-for-bot-api-d26faf9bf064)**_  to generate a create a bot and generate token to use it in the code. If you are unable to read the blog in normal mode, use the incognito mode of your browser.

### step 6:
Update the token in the code, **BOT_TOKEN**. And also update the ***cookie.json*** with correct path in the code. After updating the details,  run the python script - ***_[bingbot.py](https://github.com/amazingpaddy/chatgpt-telegram-bot/blob/main/bingbot.py)_*** using an IDE or command prompt.

Update your telegram id in the authorized_id list in the code.
**`authorized_id = ['<your telegram username without @>']`**. **You can give access to your closed ones by adding their id to the list. But its not recommended. **

For example, if my telegram userid is @exampleuserid, then update the list like **`authorized_id = ['exampleuserid']`**

Use the below command to run bot code

**`python bingbot.py`**

### step 7:
Test the code using bot.  If you follow the steps to create telegram bot, you might have got the bot link from botFather, Use the link to open the bot and click start. 

Use **`/ask <your query>`** to post a query and send it. The response will not have any reference links. 

if you want the response with reference, use **`/askref <your query>`**

Wait 2 to 3 mins to recieve response. You need to keep running the server in your laptop or cloud for bot to be working.
