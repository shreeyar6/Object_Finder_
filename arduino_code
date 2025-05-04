#include <ESP8266WiFi.h>
#include <ESP8266HTTPClient.h>
#include <TinyGPS++.h>
#include <SoftwareSerial.h>

// WiFi credentials
const char* ssid = "YOUR_SSID";
const char* password = "YOUR_PASSWORD";

// API endpoint (can be ThingSpeak or custom server)
const char* serverUrl = "http://your-api-endpoint.com/track";

// Sensor Pins
const int buzzerPin = D1;
const int ledPin = D2;
const int flamePin = D5;
const int proximityPin = D6;
const int mq5Pin = A0;  // analog gas sensor

// GPS module
SoftwareSerial gpsSerial(D7, D8); // RX, TX
TinyGPSPlus gps;

void setup() {
  Serial.begin(9600);
  gpsSerial.begin(9600);

  pinMode(buzzerPin, OUTPUT);
  pinMode(ledPin, OUTPUT);
  pinMode(flamePin, INPUT);
  pinMode(proximityPin, INPUT);

  WiFi.begin(ssid, password);
  Serial.print("Connecting to WiFi...");
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("\nConnected to WiFi");
}

void loop() {
  // Read Sensors
  int smokeValue = analogRead(mq5Pin);
  bool flameDetected = digitalRead(flamePin) == LOW;
  bool intrusion = digitalRead(proximityPin) == LOW;

  // Short-range alert
  if (flameDetected || intrusion || smokeValue > 500) {
    digitalWrite(buzzerPin, HIGH);
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(buzzerPin, LOW);
    digitalWrite(ledPin, LOW);
  }

  // Read GPS data
  while (gpsSerial.available() > 0) {
    gps.encode(gpsSerial.read());
  }

  // Send data if valid location is found
  if (gps.location.isUpdated()) {
    float lat = gps.location.lat();
    float lng = gps.location.lng();

    if (WiFi.status() == WL_CONNECTED) {
      HTTPClient http;
      String url = String(serverUrl) +
                   "?lat=" + String(lat, 6) +
                   "&lng=" + String(lng, 6) +
                   "&smoke=" + smokeValue +
                   "&flame=" + flameDetected +
                   "&intrusion=" + intrusion;

      http.begin(url);
      int httpCode = http.GET();
      if (httpCode > 0) {
        Serial.println("Data sent: " + http.getString());
      } else {
        Serial.println("HTTP error: " + String(httpCode));
      }
      http.end();
    }
  }

  delay(5000); // Update every 5 seconds
}

