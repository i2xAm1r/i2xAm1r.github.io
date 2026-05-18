---
title: "IRData Explorer Version 1.0.0 ⚡"
categories: [Github, IRDataExplorer]
tags: [Application,Python,SQLServer]
date: 2026-05-18 18:40:00 +0330
image: assets/img/Github/IRData.png
description: "دیتابیس ثبت احوال ایران:
این برنامه با دیتابیس لیک شده ثبت احوال به شما اجازه میده مشخصات افراد رو با شماره تلفن و ادرس و اسم جستجو کنید تا به تارگت مدنظرتون برسید + 20 میلیون مشخصات "
---

<h2>Projects</h2>
<ul>
  <li>
    <a href="https://github.com/i2xAm1r/IRData-Explorer" target="_blank">
    📃IRData Explorer :
    </a>

<p>

IRData Explorer is a modern desktop-based database exploration and search platform developed using Python, PySide6, and Microsoft SQL Server.  
This application is designed for fast searching across large MDF/LDF databases with a modern graphical interface, smart filtering system, and multi-database support. 🚀💻

The tool provides intelligent searching capabilities such as phone normalization, Persian text normalization, instant result filtering, CSV exporting, and dynamic database configuration.  
It was built to provide a fast and user-friendly experience for exploring and managing large SQL Server datasets without requiring users to manually write SQL queries.
</p>

  </li>
</ul>

## 🔧 Features

- **Fast Multi-Database Search**
- **SQL Server MDF/LDF Support**
- **Smart Phone Number Matching**
- **Persian Text Normalization**
- **Search by Name, Phone, Address, IDCode and more**
- **Live Filtering**
- **CSV Export**
- **Copy Selected Record**
- **Double Click Record Details**
- **Dark Theme**
- **Hacker Green Theme**
- **Config-based Database Management**
- **Windows EXE Support**

## 🎯 Key Features:

Modern graphical interface for large database searching

Supports multiple SQL Server databases simultaneously

Fast filtering and smart searching system

Automatic database attach support

Executable Windows application (.exe)

Modern dark and hacker-inspired themes

Optimized for very large database files

Supports exporting search results to CSV

---

## 📸 UI Preview

![image](https://github.com/i2xAm1r/IRData-Explorer/blob/main/Screenshot%202026-05-18%20182539.png?raw=true)

---

## 📦 Requirements

Before running IRData Explorer, make sure the following requirements are installed:

- **Windows 10 / Windows 11**
- **Microsoft SQL Server**
  - SQL Server Developer
  - or SQL Server Express
- **SQL Server Management Studio (SSMS)**  
  Optional, but recommended for manual database attach and troubleshooting.

For development/building from source:

- Python 3.10+
- PySide6
- pyodbc
- PyInstaller

Install Python dependencies:

```bash
pip install PySide6 pyodbc pyinstaller
```

---

## 🗄️ Database Setup

IRData Explorer works with SQL Server databases such as:

```text
KDB_M.mdf
KDB_M.ldf
KDB98_M.mdf
KDB98_M.ldf
```

### Manual Attach with SSMS

1. Open SQL Server Management Studio
2. Connect to your SQL Server instance
3. Right click on Databases
4. Click Attach
5. Click Add
6. Select the `.mdf` file
7. SQL Server should automatically detect the `.ldf` file
8. Click OK
9. Repeat for other databases if needed

---

## ⚙️ Configuration

The application uses a `config.json` file to detect:

- SQL Server name
- Database names
- MDF file path
- LDF file path

Example:

```json
{
    "server": "localhost",
    "databases": [
        {
            "name": "KDB_M",
            "mdf_path": "D:\\Database\\KDB_M.mdf",
            "ldf_path": "D:\\Database\\KDB_M.ldf"
        },
        {
            "name": "KDB98_M",
            "mdf_path": "D:\\Database\\KDB98_M.mdf",
            "ldf_path": "D:\\Database\\KDB98_M.ldf"
        }
    ]
}
```

### Important Path Note

In JSON files, Windows paths must use double backslashes:

```json
"D:\\Database\\KDB_M.mdf"
```

---

## 🖥️ Server Name Guide

Default SQL Server:

```json
"server": "localhost"
```

SQL Server Express:

```json
"server": "localhost\\SQLEXPRESS"
```

Custom SQL Instance:

```json
"server": "DESKTOP-123ABC\\SQLEXPRESS"
```

---

## 📁 Final Release Structure

```text
IRDataExplorer/
├── IRDataExplorer.exe
├── config.json
└── Database/
    ├── KDB_M.mdf
    ├── KDB_M.ldf
    ├── KDB98_M.mdf
    └── KDB98_M.ldf
```

---

## ⚠️ Troubleshooting

If the app cannot connect to the database:

- Make sure SQL Server is installed
- Make sure SQL Server service is running
- Make sure `config.json` is next to the `.exe`
- Make sure the server name is correct
- Make sure MDF/LDF paths are correct
- Try running the app as Administrator

---

## 📡 Social Media 

[![Telegram](https://img.shields.io/badge/Telegram-Join-blue)](https://t.me/I2xAm1r)  
[![Instagram](https://img.shields.io/badge/Instagram-Follow-red)](https://instagram.com/2xam1r)  
[![GitHub](https://img.shields.io/badge/GitHub-View-black)](https://github.com/I2xAm1r)

[![Discord server](https://discordapp.com/api/guilds/938143724565835848/embed.png?style=banner3)](https://discord.gg/WtPzSe94)

---

## 👨‍💻 Developer

Developed by **I2xAm1r**

---