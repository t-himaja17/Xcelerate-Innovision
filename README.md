# Xcelerate-Innovision – Vehicle Accident Detection and Notification System

##  Project Overview

Our project is an **IoT-based Vehicle Accident Detection and Notification System**.  
The goal is to **automatically detect accidents** and **immediately notify emergency contacts / authorities** with critical information such as:

- Accident detection event
- Vehicle location
- Time of the incident
- Basic status/alert through a Telegram bot or other channels

This helps reduce response time after an accident and can potentially save lives, especially on highways or in low-traffic areas where accidents may go unnoticed.



##  Domains & Technologies

- **Domain:** Internet of Things (IoT)
- **Technologies / Frameworks:**
  - **Arduino** (microcontroller for sensor interfacing & logic)
  - **Telegram Bot** (for sending real-time notifications/alerts)
  - **HTTP protocol / Webhooks** (for communication between Arduino-side system and cloud/bot)
  - Sensors & modules (planned examples):
    - Accelerometer / gyroscope / vibration sensor for impact detection
    - GPS module for location tracking
    - GSM / Wi-Fi module for connectivity (as applicable)
  - Optional: Buzzer / LEDs / push button for manual SOS and status indication



##  Project Progress – Checkpoints

###  Checkpoint 1 – Ideation & Setup

**Primary Idea / Concept**

> *Vehicle accident detection and notification system.*

At this stage we:
- Defined the **problem statement**: accidents often go unreported quickly, especially in remote areas or at night.
- Chose an **IoT-based approach** so that hardware in the vehicle can **autonomously detect** an accident and trigger alerts.
- Decided on **Telegram bot + HTTP** for fast and simple notifications to users and/or a central server.

**Role & Responsibility**

- I am mainly responsible for:
  - Selecting suitable **hardware components** (microcontroller, sensors, modules)
  - Connecting and testing them on **breadboard / prototype PCB**
  - Validating that sensor values are meaningful for accident detection (e.g., sudden spikes in acceleration).

**Domain**

- We finalised **Internet of Things (IoT)** as the core domain, since the system tightly integrates hardware (in vehicle), connectivity modules, and cloud services/bots.

**Technologies / Frameworks**

- Chosen stack:
  - **Arduino** as the main controller
  - **Telegram bot** as user-facing alert mechanism
  - **HTTP protocol** for sending data/alerts to cloud or bot backend
- This checkpoint ended with our **idea, domain, and high-level tech stack confirmed.**



###  Checkpoint 2 – Planning & Design

**Current Development Stage**

- We are in the **Planning and Design** phase.
- Activities done here:
  - Designing the **overall architecture**:
    - Accident detection sensors → Arduino → Communication module (GSM/Wi-Fi) → Server/Telegram bot → User/Contacts
  - Deciding **data flow**:
    - What data is captured (impact value, time, location)
    - When an accident is considered “valid” (thresholds, filtering false positives)
    - What exactly is sent in the alert message (vehicle ID, location link, timestamp, severity if possible).

**Team Collaboration**

- **All team members are actively contributing.**
- Work division example:
  - One member focuses on **hardware & sensor integration**
  - Another on **Telegram bot / backend logic**
  - Another on **testing, documentation, and presentation**
- Regular discussions are done to align hardware capabilities with software features.

**Mentorship & Support**

- We have **sufficient support**:
  - Access to mentors/seniors for clarifying IoT and microcontroller doubts.
  - Guidance on selecting correct modules and safety considerations.

**Timeline Status**

- We are **on schedule** as per hackathon milestones:
  - Idea finalised ✔
  - Components list prepared ✔
  - Architecture and flow decided ✔

**Resources & Tools**

- **Adequate resources** are available:
  - Required sensors, Arduino board, modules
  - Development tools (Arduino IDE, internet connectivity, etc.)
- No critical blocker due to lack of tools at this stage.



###  Checkpoint 3 – Technical Challenges & Component Procurement

**Technical Challenges**

Main challenge identified:

> *Choosing which microcontroller and modules to use.*

In more detail:
- Deciding between different **Arduino boards** (e.g., Uno vs. Nano vs. NodeMCU/ESP32, etc.) based on:
  - Number of I/O pins needed
  - Built-in communication (Wi-Fi/Bluetooth) vs. external GSM module
  - Power consumption and size for mounting in a vehicle
- Selecting compatible **communication module**:
  - Whether to use GSM (SIM800, etc.) or Wi-Fi (ESP-based) depending on:
    - Network availability in real scenarios
    - Ease of interfacing with Telegram / HTTP endpoints
- Ensuring that:
  - The microcontroller can **reliably read sensor values** at required speed.
  - The module can **send data quickly** when an accident is detected.
- Considering **power supply and stability**, since in-vehicle conditions can be noisy.

**How We Are Addressing Them**

- Comparing specs of shortlisted boards and modules.
- Checking **library support**, community examples, and sample codes.
- Planning small prototype tests with:
  - Sensor → Arduino → Serial output
  - Simple HTTP request / Telegram message to check end-to-end latency.

**Progress Update**

> *We have gathered all the components.*

- Microcontroller board(s) purchased.
- Sensors for accident detection acquired (e.g., accelerometer/vibration sensor).
- Communication module and necessary wires, breadboard, power supply have been collected.
- Work now shifts from planning → **hardware assembly and initial coding**.



###  Checkpoint 4 – Implementation, Integration & Testing

**Feature Completion**

- Status: **Most key features implemented.**
- Implemented / In-progress features:
  - Accident detection algorithm using sensor data  
    - Detects sudden impact or abnormal change above a certain **threshold**.
  - Triggering a **notification event** when an accident is detected.
  - Communication from Arduino to backend / Telegram bot using **HTTP or relevant API**.
  - Sending an **alert message** (and optionally location) to predefined users or chat.
- Some features still in progress/refinement:
  - Fine-tuning thresholds to reduce **false positives** (e.g., speed breakers / potholes).
  - Handling edge cases like **network failure** or **power loss**.

**Integration and System Testing**

- Status: **Integration in progress.**
- Activities:
  - Connecting all components into a single working prototype:
    - Sensors + Arduino + communication module + power.
  - Ensuring that:
    - Accident detection code runs continuously.
    - Once triggered, notification is reliably sent via Telegram/HTTP.
  - Verifying sequence:
    1. Simulate impact (shake/drop test or manual trigger).
    2. Arduino detects event.
    3. Communication module sends data.
    4. Telegram bot / backend receives and posts alert.
- Watching for timing, reliability, and potential crashes in the code.

**User Experience & Interface**

- Focus currently is on **hardware prototype and basic interaction**, so we consider this as:

> *We got a hardware prototype (and basic interface).*

- For now:
  - Hardware indicators like **buzzer** indicate system status (armed, accident detected, alert sent).
  - Telegram chat acts as a **simple user interface**:
    - User receives messages like *“Accident detected for Vehicle X at [location link]”*.
  - UI/UX will be further refined after core functionality is stable.

**Testing and Quality Assurance**

- Status: **Initial testing done, more is needed.**
- Types of tests:
  - **Functional tests**:
    - Does the system detect an impact?
    - Is the notification sent every time?
  - **False positive tests**:
    - Normal driving conditions simulated by moderate shakes.
    - Check that system does not trigger alerts unnecessarily.
  - **Connectivity tests**:
    - What happens if network is temporarily unavailable?
    - Ensure system retries or logs the failure.
- Observations from testing will be used to tune thresholds and improve reliability.

**Preparation for Presentation**

- Status: **Working on presentation.**
- Current work:
  - Preparing **slides** explaining:
    - Problem, solution, architecture, and demo flow.
  - Planning a **live demo** or recorded video:
    - Show how accident is simulated and notification received.
  - Adding clear explanation of **real-world impact and scalability**.

**Team Readiness and Confidence**

- Status: **Somewhat confident, need more rehearsal.**
- The team:
  - Understands the system well and has a working prototype.
  - Needs a bit more time to:
    - Polish explanation and pitch.
    - Rehearse demo flow so that everything fits in the hackathon time limit.
- With a few more practice rounds and minor tweaks, we expect to be fully ready.

###  Checkpoint 5– 
- **Final testing in process, almost everything is ready**
- Implemented almost all of the features mentioned in chekpoint 3 and 4.
- Currently working on connecting the IP address to get access to data (local IP address).
- All the hardware setup is done,software code for various modules is done.
- feeding this code to the microcontroller (ESP32).

### Arduino IDE Code -
/* Vehicle Crash Logger with MPU6050 + Neo-6M GPS + LCD + Webserver
   Pins used:
   - I2C (MPU6050 + 16x2 I2C LCD): SDA = D2, SCL = D1  -> Wire.begin(D2, D1)
   - GPS: SoftwareSerial ss(D6, D5)  (RX = D6, TX = D5)
*/

#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <TinyGPS++.h>
#include <SoftwareSerial.h>
#include <ESP8266WiFi.h>
#include <UniversalTelegramBot.h>

#define BUZZER_PIN D8

//
// ---- USER CONFIG ----
const char* ssid     = "Airtel_123";
const char* password = "12356790";
// ----------------------

LiquidCrystal_I2C lcd(0x27, 16, 2);
TinyGPSPlus gps;
SoftwareSerial ss(D6, D5);   // GPS: RX=D6, TX=D5

WiFiServer server(80);

// ----- Telegram credentials -----
//String BOT_TOKEN = "7963726070:AAEBbKqE-CxdJWnLgo_0irH3m3a-hPAzvzU";
//String CHAT_ID = "5558370076";

String BOT_TOKEN = "8451372665:AAEiXYCURnH6E8oqWUX4F0O3Hg9YrE1aGHs";
String CHAT_ID = "1346004700";

WiFiClientSecure clientTCP;
UniversalTelegramBot bot(BOT_TOKEN, clientTCP);

// MPU6050
const uint8_t MPU_ADDR = 0x68;
int16_t rawAx, rawAy, rawAz;
float AccX, AccY, AccZ;

// Keep last valid GPS fix
String lastLat = "0.000000";
String lastLon = "0.000000";
String lastTime = "--:--:--";
String lastDate = "--/--/----";

// Crash logging (circular buffer)
const int MAX_LOGS = 20; // As per RAM Availability 
struct CrashLog {
  int id;
  String position;
  String latitude;
  String longitude;
  String date;
  String time;
};
CrashLog logs[MAX_LOGS];
int logsCount = 0;     // how many logs stored (<= MAX_LOGS)
int logsNext = 0;      // index to insert next log (0..MAX_LOGS-1)

// Crash detection/re-arm control
unsigned long lastCrashMillis = 0;
const unsigned long CRASH_DEBOUNCE_MS = 3000; // block re-logging for this duration
bool crashArmed = true; // allow logging when true

// Helper --------------------------------------------------------------------
String getPositionFromAcc(float ax, float ay, float az) {
  // Calculate pitch and roll in degrees
  float pitch = atan2(ax, sqrt(ay*ay + az*az)) * 180.0 / PI;
  float roll  = atan2(ay, sqrt(ax*ax + az*az)) * 180.0 / PI;

  // Orientation detection using tilt angles
  if (pitch > 40)  return "Left";         // leaning forward
  if (pitch < -40) return "Right";          // leaning backward
  if (roll > 40)   return "Back";         // tilting right
  if (roll < -40)  return "Front";          // tilting left

  // Flat/down position
  if (az < 0.3)    return "Down";
  return "Normal";
}

void saveCrash(String pos) {
  // store next entry in circular buffer
  int idx = logsNext;
  logs[idx].id = (logsCount < MAX_LOGS) ? (logsCount + 1) : ( (logsNext==0) ? MAX_LOGS : logsNext );
  // we prefer sequential ids in output (1..n) but when buffer wraps ids will reflect order of filling
  // simpler: store incremental serial number using a separate counter:
  static int serialNo = 0;
  serialNo++;
  logs[idx].id = serialNo;

  logs[idx].position = pos;
  logs[idx].latitude = lastLat;
  logs[idx].longitude = lastLon;
  logs[idx].date = lastDate;
  logs[idx].time = lastTime;

  logsNext = (logsNext + 1) % MAX_LOGS;
  if (logsCount < MAX_LOGS) logsCount++;

  // print to serial
  Serial.println(F("=== Crash Recorded ==="));
  Serial.print(F("S.No: ")); Serial.println(logs[idx].id);
  Serial.print(F("Position: ")); Serial.println(pos);
  Serial.print(F("Lat: ")); Serial.println(lastLat);
  Serial.print(F("Lon: ")); Serial.println(lastLon);
  Serial.print(F("Date: ")); Serial.println(lastDate);
  Serial.print(F("Time: ")); Serial.println(lastTime);
  Serial.println(F("======================"));
}

void serveClient(WiFiClient &client) {
  // read request (simple)
  String req = client.readStringUntil('\r');
  // skip rest of request headers
  while (client.available()) client.readStringUntil('\n');

  // Build HTML (small, memory conscious)
  String html = "HTTP/1.1 200 OK\r\nContent-Type: text/html\r\n\r\n";
  html += "<!doctype html><html><head><meta charset='utf-8'>";
  html += "<meta http-equiv='refresh' content='5'>"; // auto-refresh every 5s
  html += "<title>Crash Logs</title>";
  html += "<style>body{font-family:Arial,Helvetica,sans-serif;margin:10px}table{border-collapse:collapse;width:100%}th,td{border:1px solid #444;padding:6px;text-align:center}th{background:#eee}</style>";
  html += "</head><body>";
  html += "<h2 style='text-align:center'>Vehicle Crash Log</h2>";
  html += "<p>Last GPS: " + lastLat + ", " + lastLon + " | Time: " + lastTime + " | Date: " + lastDate + "</p>";
  html += "<table><tr><th>S.No</th><th>Position</th><th>Latitude</th><th>Longitude</th><th>Date</th><th>Time</th><th>Map</th></tr>";

  // print logs in chronological order (oldest -> newest)
  // If buffer hasn't wrapped, logs are 0..logsCount-1
  // If wrapped, logsNext points to next insertion index; oldest is logsNext, newest is logsNext-1
  int printed = 0;
  if (logsCount > 0) {
    int start;
    if (logsCount < MAX_LOGS) {
      start = 0;
    } else {
      start = logsNext; // oldest item
    }
    for (int i = 0; i < logsCount; ++i) {
      int idx = (start + i) % MAX_LOGS;
      html += "<tr>";
      html += "<td>" + String(logs[idx].id) + "</td>";
      html += "<td>" + logs[idx].position + "</td>";
      html += "<td>" + logs[idx].latitude + "</td>";
      html += "<td>" + logs[idx].longitude + "</td>";
      html += "<td>" + logs[idx].date + "</td>";
      html += "<td>" + logs[idx].time + "</td>";
      html += "<td><a href='https://maps.google.com/?q=" + logs[idx].latitude + "," + logs[idx].longitude + "' target='_blank'>Open</a></td>";
      html += "</tr>";
      printed++;
      // safe guard
      if (printed > MAX_LOGS) break;
    }
  }

  html += "</table><p style='font-size:12px;color:#666'>Auto-refresh every 5s</p>";
  html += "</body></html>";

  client.print(html);
  client.stop();
}

// ----------- SEND TELEGRAM ALERT -----------
void sendTelegramCrash(String direction) {

  String msg = "🚨 *CRASH DETECTED* 🚨\n\n";
  msg += "📍 Position: *" + direction + "*\n";
  msg += "🌐 Latitude: " + lastLat + "\n";
  msg += "🌐 Longitude: " + lastLon + "\n";
  msg += "📅 Date: " + lastDate + "\n";
  msg += "⏰ Time: " + lastTime + "\n\n";
  msg += "🔗 Google Maps:\n";
  msg += "https://maps.google.com/?q=" + lastLat + "," + lastLon;

  bot.sendMessage(CHAT_ID, msg, "Markdown");
}

// Setup ---------------------------------------------------------------------
void setup() {
  Serial.begin(115200);
  delay(50);

  // I2C on your pins
  Wire.begin(D2, D1);

  // Buzzer pin
  pinMode(BUZZER_PIN, OUTPUT);

  // LCD
  lcd.init();
  lcd.backlight();
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("Crash Logger Boot");
  delay(800);

  // GPS Serial
  ss.begin(9600);

  // Wake MPU6050
  Wire.beginTransmission(MPU_ADDR);
  Wire.write(0x6B);
  Wire.write(0);
  Wire.endTransmission(true);

  // WiFi connect
  WiFi.mode(WIFI_STA);
  WiFi.begin(ssid, password);
  lcd.clear();
  lcd.print("WiFi connecting");
  Serial.print(F("Connecting to "));
  Serial.println(ssid);

  unsigned long wifiStart = millis();
  while (WiFi.status() != WL_CONNECTED) {
    delay(300);
    Serial.print(".");
    lcd.print(".");
    // after long timeout we still continue (GPS + logging will work offline)
    if (millis() - wifiStart > 20000) break;
  }

  if (WiFi.status() == WL_CONNECTED) {
    Serial.println();
    Serial.print(F("Connected. IP: "));
    Serial.println(WiFi.localIP());
    lcd.clear();
    lcd.print("IP:");
    lcd.setCursor(0,1);
    lcd.print(WiFi.localIP());
    server.begin();

    clientTCP.setInsecure();  // IMPORTANT for Telegram SSL
    delay(2000);
  } else {
    Serial.println();
    Serial.println(F("WiFi not connected (continue without web)"));
    lcd.clear();
    lcd.print("WiFi failed");
    delay(1000);
    lcd.clear();
  }



  delay(1000);
}

// Loop ----------------------------------------------------------------------
void loop() {
  // ---- read GPS bytes and update last valid fix ----
  while (ss.available() > 0) {
    char c = ss.read();
    gps.encode(c);
  }
  if (gps.location.isValid()) {
    lastLat = String(gps.location.lat(), 6);
    lastLon = String(gps.location.lng(), 6);
  }
  if (gps.time.isValid()) {
    // UTC time from GPS, convert to hh:mm:ss string
    int h = gps.time.hour();
    int m = gps.time.minute();
    int s = gps.time.second();
    // Convert to local if needed (example IST +5:30). Comment out if you want UTC.
    m += 30;
    if (m >= 60) { m -= 60; h++; }
    h += 5;
    if (h >= 24) h -= 24;
    lastTime = (h < 10 ? "0" + String(h) : String(h)) + ":" +
               (m < 10 ? "0" + String(m) : String(m)) + ":" +
               (s < 10 ? "0" + String(s) : String(s));
  }
  if (gps.date.isValid()) {
    int d = gps.date.day();
    int mo = gps.date.month();
    int yr = gps.date.year();
    lastDate = (d < 10 ? "0" + String(d) : String(d)) + "/" +
               (mo < 10 ? "0" + String(mo) : String(mo)) + "/" +
               String(yr);
  }

  // ---- read MPU6050 accelerations ----
  Wire.beginTransmission(MPU_ADDR);
  Wire.write(0x3B);
  Wire.endTransmission(false);
  Wire.requestFrom(MPU_ADDR, 6, true);

  rawAx = Wire.read() << 8 | Wire.read();
  rawAy = Wire.read() << 8 | Wire.read();
  rawAz = Wire.read() << 8 | Wire.read();

  AccX = rawAx / 16384.0;
  AccY = rawAy / 16384.0;
  AccZ = rawAz / 16384.0;

  // ---- update LCD with last-known coordinates ----
  lcd.clear();
  lcd.setCursor(0,0);
  lcd.print("Lat:");
  lcd.print(lastLat.substring(0,6));
  lcd.setCursor(0,1);
  lcd.print("Lon:");
  lcd.print(lastLon.substring(0,6));

  // ---- position & crash detection ----
  String pos = getPositionFromAcc(AccX, AccY, AccZ);

  unsigned long now = millis();

  if (pos != "Normal") {
    // crash candidate - check debounce & arming
    if (crashArmed && (now - lastCrashMillis > CRASH_DEBOUNCE_MS)) {
      // register crash
      lcd.clear();
      lcd.print("CRASH!");
      lcd.setCursor(0,1);
      lcd.print(pos);
      saveCrash(pos);

      lastCrashMillis = now;
      crashArmed = false; // wait until orientation returns to Normal to re-arm
      //delay(1000);         // small pause for stability
      tone(BUZZER_PIN, 2000); //pin, frequency, duration (0 to 2k freq.) 1600
      delay(2000);
      noTone(BUZZER_PIN);
      sendTelegramCrash(pos);
    }
  } else {
    // normal orientation: re-arm (after debounce)
    if (!crashArmed && (now - lastCrashMillis > 500)) {
      crashArmed = true;
    }
  }

  // ---- handle incoming web clients (if WiFi connected) ----
  if (WiFi.status() == WL_CONNECTED) {
    WiFiClient client = server.available();
    if (client) {
      // wait for HTTP request
      unsigned long tstart = millis();
      while (client.available() == 0 && millis() - tstart < 2000) {
        delay(1);
      }
      if (client.available()) serveClient(client);
      else client.stop();
    }
  }

  delay(200); // main loop pacing
}



2. **Architecture and design planning** (Checkpoint 2)  
3. **Component selection and procurement with technical challenge analysis** (Checkpoint 3)  
4. **Implementation of core features, integration, initial testing, and presentation preparation** (Checkpoint 4)
5. **Final working prototype testing/demo is being conducted**(Checkpoint 5)

This README section documents our journey and clearly shows the judges how **Xcelerate Innovision** has evolved from a concept into a working IoT accident detection and notification prototype.
