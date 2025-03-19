---
title: "Free server Linux building tutorial 🍃"
date: 2025-01-18 17:36:02 +0330
categories: [Learning, RDP]
tags: [Server, Linux, RDP]
description: "Create a free server with github "
image: assets/img/rdp/server.jpg
---

## How to Use a Free Server on GitHub

<h4>Hi guys, today I want to teach you how you can create a free server Linux with github.</h4>

## Steps 1
<ol>
  <li>In the first step, you need to log in to your GitHub and go to the codespaces section, then create a codespace (:</li>
  <li>In the first section, select a repository (preferably create one).</li>
  <li>In the branch section, set the default and set the region to the continent where you want the server to get an IP (random country).</li>
  <li>Depending on your hardware needs, adjust and build the machine type section.</li>
  <li>Wait a few moments for the VSCode environment to fully open.</li>
</ol>

<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/rdp/codespaces.png" alt="Codespaces" width="850" height="200">
</div>

<span style="color: yellow;">Now go to the codespaces section and disable the auto delete codespaces checkbox.</span>

<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/rdp/delete.png" alt="Disable auto delete" width="850" height="200">
</div>

## Terminal Commands
<p>Now we are dealing with this part called the terminal. Execute the commands one by one and wait until the terminal finishes working before moving on to the next command.</p>

<span style="color: yellow;">Tip:</span> How do we know when the terminal is finished? As in the picture below, the line of code ends with <span style="color: yellow;">$</span>, meaning the terminal is ready to enter!

<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/rdp/vscode.png" alt="VSCode Terminal" width="850" height="200">
</div>

<ol>
  <li><code>sudo apt update</code></li>
  <li><code>sudo apt upgrade</code></li>
  <li><code>sudo DEBIAN_FRONTEND=noninteractive \</code></li>
  <li><code>   apt install --assume-yes xfce4 desktop-base dbus-x11 xscreensaver</code></li>
  <li><code>sudo apt install ubuntu-desktop</code></li>
  <li><code>sudo apt install screen</code></li>
  <li><code>wget https://dl.google.com/linux/direct/chrome-remote-desktop_current_amd64.deb</code></li>
  <li><code>sudo apt install ./chrome-remote-desktop_current_amd64.deb</code></li>
  <li><code>sudo bash -c 'echo "exec /etc/X11/Xsession /usr/bin/xfce4-session" > /etc/chrome-remote-desktop-session'</code></li>
  <li><code>sudo service lightdm stop</code></li>
</ol>

## Steps 2
<ol>
  <li>Now you need to go to the <a href="https://remotedesktop.google.com/headless" target="_blank">Remote Desktop site</a> and in the setup via SSH section, click "Begin", then "Next", and "Authorize".</li>
  <li>Copy the link in the Debian Linux section.</li>
</ol>

<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/rdp/remote.png" alt="Remote Desktop Site" width="850" height="200">
</div>

<ol start="3">
  <li>Enter the copied link into the terminal.</li>
  <li>Enter a 6-digit PIN when prompted, and do not forget it.</li>
  <li>It should say <span style="color: yellow;">"Host started successfully"</span>. Then go back to the site, and in the remote access section, you should see the remote access created for you.</li>
</ol>

<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/rdp/device.png" alt="Remote Access Device" width="750" height="200">
</div>

### Testing Your Server
<p>Now you click on codespace and enter your PIN.</p>

<div style="text-align: center; margin: 20px 0;">
    <code style="font-size: 20px; font-weight: bold; padding: 20px;">
        And boom boom, your server is ready to use 🥳🤝
    </code>
</div>

<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/rdp/linux.png" alt="Linux Server Ready" width="750" height="200">
</div>

<div style="text-align: center; margin: 20px 0;">
    <code style="font-size: 20px; font-weight: bold; padding: 20px;">
        speedtest server
    </code>
</div>

<div style="text-align: center; margin: 20px 0;">
    <img src="assets/img/rdp/speedtest.png" alt="Speed Test" width="750" height="300">
</div>

<div style="text-align: center; margin-top: 20px; font-family: Arial, sans-serif; font-size: 18px;">
    <p>If you liked this tutorial, I would appreciate it if you could support me on social media. 😊</p>
</div>

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