# 📡 APRS_Wx_v2 — Powered by Python

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
