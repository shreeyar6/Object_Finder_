# Object_Finder_
This Project aims to design an IOT based product which helps to track misplaced objects

# 🔍 Smart Object Finder

An IoT-based embedded system that helps users track and locate misplaced or at-risk objects using real-time data and alerts. Equipped with sensors for fire, smoke, proximity, and integrated with GPS and a user-friendly app interface, the system offers both **short-range** (buzzer/LED) and **long-range** (GPS/API) tracking.

---

## 🚀 Project Overview

In today’s fast-paced world, it’s easy to misplace or lose valuable items. The Smart Object Finder offers a **quick and intelligent solution** using sensors, location tracking, and an app interface to pinpoint and alert users of an object’s whereabouts.

---

## ✅ Objectives

- Track object location using GPS and display it via an API/App
- Alert users with LED/Buzzer for short-range tracking
- Detect fire and smoke using flame and gas sensors
- Sense proximity intrusions for anti-theft protection
- Provide 24/7 cloud-based access through the ESP8266 Wi-Fi module

---

## ⚙️ Workflow


---

## 📦 Components Used

| Component            | Purpose |
|----------------------|---------|
| **ESP8266-12E**      | Wi-Fi enabled microcontroller for real-time cloud communication |
| **Buzzer (Piezo)**   | Short-range audible alert |
| **LED**              | Short-range visual alert |
| **MQ5 Gas Sensor**   | Smoke & gas detection (LPG, CH4, CO, Alcohol) |
| **Flame Sensor**     | Detects visible flame between 760–1100 nm |
| **IR Proximity Sensor** | Detects objects within 2–20 cm |
| **Neo 6M GPS Module**| Tracks object with GPS coordinates |
| **Custom API/App**   | For tracking and device control |

---

## 🔧 Methodology

- **ESP8266-12E** is used for Wi-Fi communication and data transmission.  
- **GPS (Neo 6M)** gives coordinates for object location, processed via Google Maps API.  
- **Smoke sensor** alerts in case of harmful gases like LPG, CO.  
- **Flame sensor** detects open flame; triggers alerts via app.  
- **IR-based proximity sensor** triggers when intruders breach the set distance.  
- **Buzzer and LED** help find nearby objects manually or through the app.  
- **API/App Interface** enables remote monitoring and device control.  

---

## 📲 Application Interface

A simple mobile application:
- Displays live location on map  
- Allows control of buzzer/LED (individually or simultaneously)  
- Receives real-time alerts from sensors  

---

## 📍 Results

- Successfully detects and alerts fire, smoke, and unauthorized proximity.  
- Accurately shows GPS coordinates via mobile app/API.  
- Allows easy control of object finder using smartphone interface.  

---

## 💡 Future Enhancements

- Add **GSM module** for SMS-based tracking in no-WiFi zones  
- Integrate **speech recognition** for hands-free tracking  
- Create a **compact PCB version**  
- Add **waterproof casing** for daily rugged use  

---

## 📚 References

- [Circuit Digest - Track location with NodeMCU](https://circuitdigest.com/microcontroller-projects/how-to-track-location-with-nodemcu-using-google-map-api)  
- [MIT App Inventor & Arduino Guide](https://community.element14.com/members-area/personalblogs/b/blog/posts/mit-app-inventor-and-arduino-part-2---send-data-from-arduino-to-android-and-display)  
- [Electronic Wings - Bluetooth with NodeMCU](https://www.electronicwings.com/nodemcu/hc-05-bluetooth-module-interfacing-with-nodemcu)  
- YouTube tutorials on IoT and sensor interfacing  
- [Thingspeak](https://thingspeak.com)  
- [Arduino.cc](https://www.arduino.cc)  
- [Robu.in](https://www.robu.in)  

---

## 📸 Screenshots & Output

> *(Insert screenshots here using the format below)*

```markdown
![App Control](images/app_control.png)
![Hardware Setup](images/hardware_setup.jpg)
