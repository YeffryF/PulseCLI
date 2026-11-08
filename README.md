# PulseCLI — Biometric & Habit Correlation Engine

**PulseCLI** *(formerly Vitality Pattern Finder)* is a C++ command-line analytics application that tracks mood-related data (stress, energy, sleep, and activities) and transforms it into structured insights using statistical analysis, correlation modeling, and trend detection.

The system is designed to move beyond simple logging by analyzing relationships between behaviors and internal states, helping users understand how daily actions influence overall performance and well-being.

---

## Key Features

* **Mood Data Logging (SQLite Database):** Stores stress, energy, sleep, notes, and activity triggers with persistent SQL-based storage.
* **Trigger-Based Behavior Tracking:** Associates moods with user-defined activities (e.g., “exam”, “gym”, “work”) and groups entries by behavior to identify patterns.
* **Statistical Analysis Engine:** Computes averages for stress, energy, and sleep, tracks 14-day trend comparisons (weekly performance shifts), and calculates rolling performance momentum.
* **Correlation Analysis System:** Measures relationships between variables using Pearson correlation ($r$) (e.g., Energy ↔ Sleep, Energy ↔ Stress, Sleep ↔ Stress) to identify primary behavioral drivers.
* **Insight Generation Engine:** Converts statistical outputs into human-readable system reports and classifies system states (e.g., overload, stability, peak performance).
* **Report System (OOP Architecture):** Uses an inheritance-based `Report` system for structured output formatting, cleanly separating analysis logic from the presentation layer.

---

## Technical Architecture

The project is built using Object-Oriented Programming (OOP) principles and layered system design:

* **`MoodEntry` Class:** Core data model representing a single user log entry (stress, energy, sleep, triggers, notes, timestamps).
* **`DatabaseManager` Class:** Handles SQLite database operations and structured insertions/retrievals via SQL queries.
* **`AnalyticsEngine` Class:** Core computation layer for statistical averages, correlation analysis, trend detection, and system insight generation.
* **`Report` System (Inheritance):** Base `Report` class defining shared structure (headers/footers) with derived classes implementing specific analytics views.
* **`AppController` Class:** Manages user interaction flow, connecting UI inputs with analytics and database layers.

---

## Data Model

Each logged entry captures:
* **Stress Level:** 1–5 scale
* **Energy Level:** 1–5 scale
* **Sleep Hours:** 0–24 hours
* **Activity Triggers:** Custom tags
* **Optional Notes & Timestamp**

---

## Download & Pre-Compiled Binaries

If you prefer to run the application immediately without compiling from source, pre-compiled binaries are available below:
* **[Download PulseCLI Executables (Google Drive)](https://drive.google.com/drive/folders/1UAcX7gNLYR6_BRLjxWXVZ0XXvxGaCnPI?dmr=1&ec=wgc-drive-%5Bmodule%5D-goto)**

### Installation & Execution Guide

#### **Mac Instructions**
1. Download the `.zip` archive from the Google Drive link above to a clean location (such as your `Downloads` folder).
2. Open **Terminal**.
3. Type `cd ` (with a space after it), then drag and drop the extracted folder from Finder straight into the Terminal window, and press **Enter**. *(Example: `cd /Users/username/Downloads/VitalitySystem_v1`)*
4. Unlock the executable permission by running:
   ```bash
   chmod +x ./VitalityPF
