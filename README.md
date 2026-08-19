# 📡 APRS_Wx_v3 — Powered by Python

![Python](https://img.shields.io/badge/-Python-3776AB?logo=python&logoColor=white) **(Windows Only)**

## 🧠 Zero Hardware. Zero Hardcoding. Zero Hassle.

No sketches, no soldering, and absolutely **no library dependencies!** 😎

Just a lightweight, plug-and-play **dual-station APRS weather beacon** — configurable using **any text editor**.

The software fetches weather and air-quality data from **Open-Meteo**, calculates the **Indian AQI**, creates APRS weather packets, and submits the data to **APRS-IS**.

---

## 📢 Latest Update — 17-August-2026

- 📡 Added support for **two independent APRS weather stations**.
- 🌦️ Each station uses its own **latitude and longitude** for weather and air-quality data.
- 📻 Each station can use its own **APRS callsign and passcode**.
- 🔢 Station-1 uses **SSID `-13`**.
- 🔢 Station-2 uses **SSID `-1`**.
- 🔄 Both stations are processed automatically at the configured interval.
- 🌐 Added multiple APRS-IS servers with automatic fallback/retry.

---

## 💡 No Installation Required

Runs directly as a **portable application** — from your PC or even a **USB pendrive**. 🧳💻

Configure the stations using `config.ini` and run the application.

---

## 🔧 Dependencies

> **None for the standalone application.**
>
> The project is designed to be packaged as a standalone executable, so the end user does not need to install Python or additional libraries.

The Python source uses standard Python functionality together with `requests` for fetching data from Open-Meteo.

---

## ⚙️ Configuration

The application uses a single `config.ini` file.

The configuration supports **two APRS weather stations**:

- `[Station-1]`
- `[Station-2]`

Each station has its own:

- 📍 Latitude
- 📍 Longitude
- 📡 APRS callsign
- 🔐 APRS passcode

A common transmission interval is used for both stations.

---

## ⚙️ Configuration Steps

1. 📦 **Download** the `aprs.zip` folder from this repository and **extract** it to any location on your system.  
         You’ll find both **`aprs.exe`** and **`config.ini`** in the same folder.
   
   ![extract2](https://github.com/user-attachments/assets/9c8de663-d42a-48d6-9d38-940a3818e5d0)
3. 📝 Open **`config.ini`** in your favorite text editor (e.g. Notepad, VS Code, Notepad++).
4. ✏️ Fill in the following fields for both stations:
   - 📍 **Latitude** & **Longitude**
   - 📡 **User Callsign without SSID**
   - 🔐 **APRS Passcode**
   - ⏱️ **Time Interval (in minutes)**
5. 💾 Save the file.
6. 🚀 Run **`aprs.exe`** — just like any other software!

   


> [!NOTE]
> Once your callsign & passcode are verified, your WX station will automatically appear on [**aprs.fi**](https://aprs.fi).

---

## 📝 `config.ini` Example

```ini
[Station-1]

# Latitude of the station  ex:12.979770
lat-1 = 00.00000

# Longitude of the station ex:77.590868
lon-1 = 00.00000

# User callsign for APRS
user-1 = VUxxxxx

# Password or passcode for APRS
pass-1 = 00000

#########################


[Station-2]

# Latitude of the station  ex:12.979770
lat-2 = 00.00000

# Longitude of the station ex:77.590868
lon-2 = 00.00000

# User callsign for APRS
user-2 = VUxxxxx

# Password or passcode for APRS
pass-2 = 00000

#########################

# time interval in minutes (5-30)
# Recommended: 20
interval = 20
```


---
### 🚀 Add to Startup (Windows)

To automatically start **APRS_Wx_v2** whenever you log into Windows:

1. Create a folder on your **C:** drive (for example, `C:\APRS`) and move the extracted **`aprs.exe`** and **`config.ini`** files into this folder.
2. Right-click **`aprs.exe`** and select **Create shortcut**.
   - If Windows asks to place the shortcut on the desktop instead, click **Yes**.
   - A shortcut named **`aprs.exe - Shortcut`** (or similar) will be created on your desktop.
3. Open the Windows Startup folder:
   - Press **Win + R**
   - Type:
     ```text
     shell:startup
     ```
   - Press **Enter**.

4. Copy the shortcut from your desktop and paste it into the **Startup** folder.
5. Restart your computer. **APRS_Wx_v2** will automatically launch when you log in.
6. After restarting, open **[aprs.fi](https://aprs.fi)** to verify that your weather station data is being uploaded successfully.

> **Note:** It is recommended to place a **shortcut** in the Startup folder rather than moving the actual `aprs.exe` file. This keeps the program in its original location while allowing Windows to launch it automatically at login.

---
