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

- **My Role in the Team:**  
  *Setting up of hardware components* – wiring sensors and modules, configuring the Arduino, ensuring reliable power and connections, and supporting hardware testing.



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
  - Hardware indicators like **LEDs / buzzer** indicate system status (armed, accident detected, alert sent).
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


2. **Architecture and design planning** (Checkpoint 2)  
3. **Component selection and procurement with technical challenge analysis** (Checkpoint 3)  
4. **Implementation of core features, integration, initial testing, and presentation preparation** (Checkpoint 4)

This README section documents our journey and clearly shows the judges how **Xcelerate Innovision** has evolved from a concept into a working IoT accident detection and notification prototype.
