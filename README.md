# Airport Departure Simulation & Optimization Project

This repository contains a comprehensive **Modelling and Simulation Project** focused on optimizing passenger throughput and minimizing waiting times at an airport departure terminal. The project covers the entire simulation lifecycle: operational bottleneck identification, empirical data collection, statistical input analysis (distribution fitting), Rockwell Automation Arena modeling, and output analysis.

---

## 📄 Project Overview

* **Objective:** Maximize customer satisfaction by minimizing average waiting times and queue lengths at domestic and international check-in/ID areas.
* **System Components:**
    * **Entities:** Domestic and International Passengers.
    * **Attributes:** Arrival time, required service type.
    * **Resources/Personnel:** Domestic and International terminal staff (Service times follow distinct distributions).
    * **Key Performance Indicators (KPIs):** Average waiting time in queues, total time spent in the system, and personnel utilization rates.

---

## 📊 Methodology & Technical Approach

### 1. Input Data Analysis (Statistical Fitting)
Based on 100 empirical data points collected for both interarrival and service behaviors, statistical software and Chi-Square tests were implemented to determine the theoretical distributions:
* **Interarrival Time:** Fits an **Erlang Distribution** (Expression: `0.5 + ERLA(1.51, 2)`) with a square error of `0.002253`.
* **Service Time:** Fits a **Gamma/Beta Distribution** structured around calculated sample parameters (Sample Mean: `2.7`, Std Dev: `1.26`).

### 2. Simulation Modeling (Rockwell Arena)
The operational logic was built in **Rockwell Arena (`.doe`)** replicating distinct processes for domestic and international tracks.
* **Simulation Run Parameters:** 8-hour shift replication setup.
* **Resource Allocation:** Evaluated under a multi-server setup to pinpoint system capacities.

### 3. Key Findings & Output Analysis
From the generated Arena simulation reports, the system performed with the following average metrics during an 8-hour cycle:
* **Total Checked Passengers:** 241 passengers (134 Domestic, 107 International).
* **Average Waiting Time in Queues:**
    * Domestic Track Queue: `~2.1 minutes`
    * International Track Queue: `~2.4 minutes`
* **Total Time in System:**
    * Domestic Passengers: `4.9 minutes` (Value-Added Time: 2.8 min)
    * International Passengers: `6.1 minutes` (Value-Added Time: 3.7 min)

---

## 📁 Repository Structure

* `/data`: Raw data files (`interarrival time.txt`, `Service Time.txt`) and statistical analysis charts (`Data Collection.csv`).
* `projemodelllll.doe`: The functional Rockwell Arena simulation model.
* `Project Presentation`: Detailed project report documentation and presentation slides detailing the bottleneck solutions.

---

## 🛠️ Tools & Technologies Used

* **Simulation Engine:** Rockwell Automation Arena
* **Statistical Analysis:** Input Analyzer, Chi-Square Goodness-of-Fit Testing
* **Data Processing:** MS Excel / CSV Analysis

