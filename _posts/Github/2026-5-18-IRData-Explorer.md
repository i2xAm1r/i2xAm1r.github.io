---
title: "IRData Explorer Version 1.0.0 ⚡"
categories: [Github, IRDataExplorer]
tags: [Application,Python,SQLServer]
date: 2026-05-18 18:40:00 +0330
image: assets/img/Github/IRData.png
description: "Iranian DataBase Leak📑 > دیتابیس لیک شده سامانه ثبت احوال ایران و ایرانسل"
---

# 📃 IRData Explorer v1.1.0

[GitHub Repository](https://github.com/i2xAm1r/IRData-Explorer)

---

## ⚡ About Project

IRData Explorer is a modern Windows desktop application developed with **Python**, **PySide6**, and **SQL Server**.

It is designed for searching, filtering, and exploring large database files through a simple graphical interface.

The application supports:

- SQL Server MDF/LDF databases
- Microsoft Access MDB databases
- Multi-database search
- Smart phone number matching
- Persian text normalization
- CSV export
- Dark and Hacker Green themes

---

## 🚀 Features

- Fast multi-database search
- SQL Server MDF/LDF support
- Microsoft Access MDB support
- Smart phone number matching
- Persian text normalization
- Search by:
  - Name
  - Mobile
  - Telephone
  - Address
  - IDCode
  - PostCode
- Live filtering inside results
- Multiple database selection
- Auto-detect MDB tables
- CSV export
- Double click record details
- Hacker Green Theme
- Dark Theme
- Config-based database management
- Windows EXE support

---

## 📸 Screenshot

![Main Dashboard](https://github.com/i2xAm1r/IRData-Explorer/blob/main/Screenshot%202026-05-18%20182539.png?raw=true)

---

## 📦 Requirements

Before running the application, install:

- Windows 10 / 11
- Microsoft SQL Server
  - SQL Server Express
  - or SQL Server Developer
- Microsoft Access Database Engine 2016 x64

Optional but recommended:

- SQL Server Management Studio (SSMS)

For source version:

```bash
pip install PySide6 pyodbc pyinstaller
```

---

## 🗄️ Supported Database Types

### SQL Server Databases

Example files:

```text
KDB_M.mdf
KDB_M.ldf
KDB98_M.mdf
KDB98_M.ldf
```

These databases require **Microsoft SQL Server**.

---

### Microsoft Access MDB Databases

Example files:

```text
935_1.mdb
935-2.mdb
936.mdb
937.mdb
938.mdb
939.mdb
```

MDB databases do **not** require SQL Server.

They require:

```text
Microsoft Access Database Engine 2016 x64
```

---

## 🗄️ SQL Database Setup

### Step 1 — Extract Database Files

After downloading your database archive, extract the ZIP/RAR file.

You should have files like:

```text
KDB_M.mdf
KDB_M.ldf
KDB98_M.mdf
KDB98_M.ldf
```

---

### Step 2 — Install SQL Server

Install one of the following:

- Microsoft SQL Server Express
- Microsoft SQL Server Developer

Optional but recommended:

- SQL Server Management Studio (SSMS)

---

### Step 3 — Attach Database to SQL Server

1. Open **SQL Server Management Studio (SSMS)**
2. Connect to your SQL Server
3. Right click on **Databases**
4. Click **Attach**
5. Click **Add**
6. Select:

```text
KDB_M.mdf
```

7. SQL Server should automatically detect:

```text
KDB_M.ldf
```

8. Click **OK**

Repeat the same steps for:

```text
KDB98_M.mdf
```

After attaching both databases, the application can connect automatically.

---

## 📁 MDB Database Setup

MDB files do not need SQL Server attach.

You only need:

- Microsoft Access Database Engine 2016 x64
- Correct MDB paths inside `config.json`

Example:

```json
{
  "name": "MDB:935",
  "path": "D:\\MDB\\935_1.mdb"
}
```

---

## ⚙️ Configure config.json

Place `config.json` next to the EXE file.

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
  ],

  "access_databases": [
    {
      "name": "MDB:935",
      "path": "D:\\MDB\\935_1.mdb"
    },
    {
      "name": "MDB:935|2",
      "path": "D:\\MDB\\935-2.mdb"
    }
  ]
}
```

Important:

Windows paths must use double backslashes.

Correct:

```text
D:\\Database\\KDB_M.mdf
```

Wrong:

```text
D:\Database\KDB_M.mdf
```

---

## 🖥️ SQL Server Name

Default SQL Server:

```json
"server": "localhost"
```

SQL Express:

```json
"server": "localhost\\SQLEXPRESS"
```

Custom SQL instance:

```json
"server": "DESKTOP-123ABC\\SQLEXPRESS"
```

---

## 📁 Final Folder Structure

```text
IRDataExplorer/
├── IRDataExplorer.exe
├── config.json
├── icon.ico
└── Database/
```

---

## ▶️ Run Application

Run:

```text
IRDataExplorer.exe
```

If databases are already attached:

- App connects automatically

If databases are not attached:

- App tries auto attach using `config.json` paths

---

## ⚠️ Troubleshooting

If the application cannot connect:

- Make sure SQL Server is running
- Check `config.json`
- Check MDF/LDF paths
- Check MDB paths
- Check SQL Server name
- Run app as Administrator

---

## 🇮🇷 توضیحات فارسی

IRData Explorer یک برنامه دسکتاپ ویندوزی برای جستجو، فیلتر و مدیریت دیتابیس‌های بزرگ است.

این برنامه با **Python** و **PySide6** ساخته شده و از دیتابیس‌های زیر پشتیبانی می‌کند:

- SQL Server با فایل‌های MDF/LDF
- Microsoft Access با فایل‌های MDB

---

## 🚀 قابلیت‌ها

- جستجوی سریع بین چند دیتابیس
- پشتیبانی از MDF/LDF
- پشتیبانی از MDB
- جستجوی هوشمند شماره موبایل
- نرمال‌سازی متن فارسی
- جستجو بر اساس:
  - نام
  - موبایل
  - تلفن
  - آدرس
  - کدملی
  - کدپستی
- فیلتر زنده نتایج
- تشخیص خودکار Table فایل‌های MDB
- خروجی CSV
- نمایش جزئیات رکورد با دابل‌کلیک
- تم Dark
- تم Hacker Green
- مدیریت دیتابیس با config.json
- نسخه EXE ویندوز

---

## ⚙️ پیش‌نیازها

قبل از اجرای برنامه نصب کنید:

- Windows 10 / 11
- Microsoft SQL Server
- Microsoft Access Database Engine 2016 x64

اختیاری ولی پیشنهادی:

- SQL Server Management Studio

---

## 🗄️ اتصال دیتابیس SQL

برای دیتابیس‌های MDF/LDF:

1. برنامه **SSMS** را باز کنید
2. به SQL Server متصل شوید
3. روی **Databases** راست کلیک کنید
4. گزینه **Attach** را بزنید
5. روی **Add** کلیک کنید
6. فایل MDF را انتخاب کنید
7. فایل LDF معمولاً خودکار شناسایی می‌شود
8. روی **OK** بزنید

---

## 📁 دیتابیس‌های MDB

فایل‌های MDB نیازی به Attach داخل SQL Server ندارند.

فقط کافیست:

- Microsoft Access Database Engine 2016 x64 نصب باشد
- مسیر فایل‌های MDB داخل `config.json` درست تنظیم شود

---

## ▶️ اجرای برنامه

فایل زیر را اجرا کنید:

```text
IRDataExplorer.exe
```

---

## 📡 Social Media

[![Telegram](https://img.shields.io/badge/Telegram-Join-blue)](https://t.me/I2xAm1r)  
[![Instagram](https://img.shields.io/badge/Instagram-Follow-red)](https://instagram.com/2xam1r)  
[![GitHub](https://img.shields.io/badge/GitHub-View-black)](https://github.com/I2xAm1r)

[![Discord server](https://discordapp.com/api/guilds/938143724565835848/embed.png?style=banner3)](https://discord.gg/WtPzSe94)

---

## 👨‍💻 Developer

Developed by **I2xAm1r**