# 3S4P Li-ion Battery Management & Power System

## Project Overview
This repository contains the design and wiring configuration for a high-capacity 12V (nominal) battery pack. The system utilizes a 3-Series 4-Parallel (3S4P) 18650 cell arrangement, integrated with a dedicated Battery Management System (BMS) and a regulated output stage.

## Component List

### 1. Energy Storage
* **18650 Li-ion Cells (x12):** High-density rechargeable cells.
    * **Configuration:** 3S4P.
    * **Nominal Voltage:** 11.1V (3.7V per series group).
    * **Full Charge Voltage:** 12.6V.

### 2. Protection & Management
* **3S Li-ion BMS (Battery Management System):**
    * Protects against overcharge, over-discharge, and overcurrent.
    * Handles cell balancing across the three series strings.

### 3. Power Regulation & Output
* **DC-DC Buck Converter Module:** Regulates the variable battery voltage down to a stable output (e.g., 5V or 9V) for sensitive electronics.
* **Dual Power Output Jacks:** Standard DC barrel connectors for powering external devices.

### 4. Interface & Indicators
* **Momentary/Latch Push Button:** Main power toggle for the output stage.
* **LED Indicator (Red):** Status light to indicate when the output is active.
* **Resistor:** Used to limit current to the LED indicator.

### 5. Circuit Components
* **Diode:** Provides reverse polarity protection or prevents backfeeding.
* **Wiring:** High-current capacity wires for the main discharge path and signal wires for BMS sensing.

## System Architecture

### Battery Configuration
The cells are organized into three distinct groups. Each group contains four cells in parallel to increase the total capacity (Ah). These three groups are then wired in series to achieve the target voltage.

### BMS Wiring
- **B-**: Connected to the primary negative terminal of the battery pack.
- **B1 / B2**: Middle-tap connections wired to the junctions between series groups for voltage monitoring.
- **B+**: Connected to the primary positive terminal of the battery pack.
- **P- / P+**: Output terminals providing protected power to the load.

## Safety Precautions
* **Cell Matching:** Ensure all 12 cells are of the same brand, capacity, and internal resistance.
* **Insulation:** Use Kapton tape or heat shrink on all exposed solder joints to prevent accidental short circuits.
* **Charging:** Only use a dedicated Li-ion charger rated for 12.6V. Never charge the pack directly without the BMS.

## Usage
This power system is ideal for high-drain applications such as robotics, DIY portable speakers, or field-testing electronics where a stable, high-capacity 12V source is required.
