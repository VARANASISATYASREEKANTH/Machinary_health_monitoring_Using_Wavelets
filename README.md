# Machinary_health_monitoring_Using_Wavelets(Bearings and Gear Box)
Heavy equipment (pumps, motors, gearboxes, excavators, blowers, centrifuges, etc.) often operates under harsh conditions, leading to:  Wear and tear  Unexpected breakdowns  High maintenance costs  Unplanned downtime affecting productivity  The goal is early fault detection before catastrophic failure.
# Interpreting Bearing and Gearbox Faults Using Spectrograms

Spectrograms are a powerful tool for diagnosing rotating machinery faults such as **bearing defects** and **gearbox failures**. Unlike a simple FFT, spectrograms provide a **time–frequency representation** of vibration signals, making them suitable for detecting transient faults and modulations.

---

## 📊 Basics of Spectrograms
- **X-axis:** Time (s)  
- **Y-axis:** Frequency (Hz)  
- **Color intensity:** Amplitude (energy at that frequency and time)  

---

## 🛠️ Bearing Faults in Spectrograms
Rolling element bearings have characteristic defect frequencies:

- **BPFO** – Ball Pass Frequency Outer race  
- **BPFI** – Ball Pass Frequency Inner race  
- **BSF** – Ball Spin Frequency  
- **FTF** – Fundamental Train Frequency  

### 🔍 What to Look For:
- **Outer race defect**
  - Strong harmonics at **BPFO**  
  - Localized periodic energy bursts  
  - Sidebands around shaft frequency  

- **Inner race defect**
  - Harmonics at **BPFI**  
  - Continuous frequency bands  
  - Energy concentrated at higher frequencies  

- **Rolling element defect**
  - Broad frequency spread (random impacts)  
  - High-frequency modulated bands (BSF components)  

- **Cage defect**
  - Low-frequency bands at **FTF**  
  - Intermittent high-frequency sidebands  

👉 Bearing faults generally show **periodic impulses** that produce **harmonics and sidebands**.

---

## ⚙️ Gearbox Faults in Spectrograms
Gearboxes introduce strong tonal components at **gear mesh frequencies (GMF):**

- **GMF = Number of Teeth × Shaft Speed**

### 🔍 What to Look For:
- **Gear tooth wear/breakage**
  - Sideband growth around **GMF**  
  - “Comb-like” modulation patterns  

- **Eccentricity / misalignment**
  - Sidebands around GMF harmonics  
  - Low-frequency energy spread  

- **Cracked gear**
  - Localized bursts at GMF  
  - Asymmetric spectrogram patterns  

- **Multiple gear stages**
  - Multiple GMFs present  
  - Overlapping sideband patterns  

👉 Gearbox faults usually show **modulation sidebands** around GMF, unlike bearings which show **impulses and defect harmonics**.

---

## 🔄 Practical Interpretation Steps
1. Establish a **baseline** (compare with healthy spectrogram).  
2. Identify **recurring patterns**:
   - Impulses → Bearing fault  
   - Sidebands at GMF → Gearbox fault  
3. Match observed frequencies with **calculated fault frequencies** (using shaft speed, gear teeth, bearing geometry).  
4. Inspect **high-frequency ranges** for early-stage bearing faults.  
5. Track **amplitude growth** and **frequency spreading** over time.  

---

## 👀 Visual Cues
- **Bearing Faults:** Impulse-like **vertical streaks** (short bursts across frequency).  
- **Gearbox Faults:** **Horizontal bands** at GMF with **sideband combs**.  
- **Healthy Machine:** Clear, stable tonal lines (shaft harmonics, GMF) without excessive sidebands.  

---

## 🚀 Next Steps
You can simulate and visualize spectrograms in Python using vibration signals (healthy vs faulty) to get hands-on practice.  
If needed, I can provide **sample code to generate synthetic spectrograms** with annotated fault signatures.

---


# 🔧 Bearing Fault Interpretation from NASA Datasets (Spectrogram-Based)

This document provides guidance on interpreting bearing faults from **NASA Bearing Data Center** (e.g., CWRU or IMS datasets) using **spectrograms**.  
It also describes the **physical damage mechanisms** and their **operational impacts**.

---

## 📊 Fault Types & Spectrogram Interpretation

### 1. Inner Race Fault
- **Spectrogram Features**
  - Harmonics of **Ball Pass Frequency Inner Race (BPFI)**.
  - Vertical streaks aligned with shaft rotation.
  - Energy concentrated at higher frequencies.
- **Physical Damage**
  - Pitting or spalling on the **inner raceway**.
- **Impact**
  - Increased vibration, heating, and shaft imbalance.
  - Accelerated wear → shaft misalignment → possible seizure.

---

### 2. Outer Race Fault
- **Spectrogram Features**
  - Harmonics of **Ball Pass Frequency Outer Race (BPFO)**.
  - Fault frequencies appear **stable** since the outer race is stationary.
  - Energy bursts at fixed frequencies.
- **Physical Damage**
  - Localized spalling/pitting on the **outer ring**.
- **Impact**
  - High vibration and noise.
  - Stress on rolling elements → secondary ball wear.
  - Shortened bearing life, risk of catastrophic failure.

---

### 3. Ball Fault
- **Spectrogram Features**
  - Harmonics of **Ball Spin Frequency (BSF)** with **modulated sidebands**.
  - Scattered energy patterns due to ball–race impacts.
- **Physical Damage**
  - Flaking or cracks on **rolling elements** (balls).
- **Impact**
  - Uneven load distribution.
  - Erratic vibrations and potential cage damage.
  - Accelerated fatigue on both races.

---

### 4. Combined Faults (Inner + Outer, or Ball + Race)
- **Spectrogram Features**
  - Overlapping BPFI, BPFO, and BSF components.
  - Broadband dense energy across wide frequency bands.
- **Physical Damage**
  - Spalling across multiple bearing components.
- **Impact**
  - Severe vibration and heat.
  - Rapid progression to catastrophic failure.
  - Usually detected in **late-stage degradation**.

---

### 5. Health Warning / Early Faults
- **Spectrogram Features**
  - Weak harmonics and sidebands.
  - Low-energy impulses, sometimes intermittent.
- **Physical Damage**
  - Micropitting, lubrication breakdown, or micro-cracks.
- **Impact**
  - Early wear stage; if left undetected, fault growth accelerates.
  - Early detection extends bearing life.

---

## 📑 Summary Table

| Fault Type          | Spectrogram Signature                  | Physical Damage                | Impact                          |
|---------------------|----------------------------------------|--------------------------------|---------------------------------|
| **Inner Race**      | Harmonics of BPFI, vertical streaks    | Spalling/pits on inner race    | Heating, shaft imbalance        |
| **Outer Race**      | Harmonics of BPFO, stable lines        | Spalling on outer race         | High vibration, noise           |
| **Ball Fault**      | Sidebands around BSF, scattered energy | Flaking/cracks on balls        | Uneven load, cage damage        |
| **Combined Faults** | Overlapping broadband signatures       | Multiple damaged parts         | Severe, rapid failure           |
| **Early Faults**    | Weak sidebands, intermittent impulses  | Micropitting, lubrication loss | Early-stage wear, progressive   |

---

## 🚀 How to Use
1. Load the NASA/CWRU bearing vibration datasets.
2. Generate spectrograms from the vibration signals.
3. Compare observed frequencies with theoretical bearing fault frequencies:
   - **BPFI** = Ball Pass Frequency Inner Race  
   - **BPFO** = Ball Pass Frequency Outer Race  
   - **BSF** = Ball Spin Frequency  
4. Match with the **signatures above** for diagnosis.

---

## 📌 Notes
- Outer race faults show **fixed-frequency patterns** (stationary component).
- Inner race and ball faults show **modulated patterns** (rotating with shaft).
- Combined faults → require **advanced signal decomposition** (FFT, Wavelets, EMD).

---


# 🔧 NASA IMS Bearing Dataset – Characteristics

The **NASA IMS Bearing Dataset** (from the University of Cincinnati Intelligent Maintenance Systems Center) is widely used for **bearing fault diagnostics** and **prognostics**.  
It provides full life-cycle vibration data of bearings running under constant load until **failure**.

---

## 📂 1. Dataset Setup
- **Source**: University of Cincinnati, IMS Center in collaboration with NASA Ames.  
- **Purpose**: Study bearing degradation from **healthy condition → fault initiation → failure**.  
- **Test Rig**:
  - Rotating shaft driven by a 2 hp motor.
  - Shaft supported by **four bearings** (Rexnord ZA-2115 double-row bearings).
  - Bearings numbered **1 to 4** (left to right).
  - Bearing **3** typically fails first.

---

## ⚙️ 2. Operating Conditions
- **Load**: Constant radial load of **6000 lbs** applied to the shaft via a spring.  
- **Rotational Speed**: ~2000 rpm (constant).  
- **Lubrication**: Oil circulation system.

---

## 🎛️ 3. Sensors & Sampling
- **Sensors**: Accelerometers mounted on the bearing housings.  
- **Sampling Frequency**: **20 kHz** (20,480 Hz).  
- **Measurement Duration**: 1-second recordings every **10 minutes**.  
- **Channels**: **4 vibration channels** (one per bearing).  
- **Data Format**: `.mat` files (MATLAB format).  

---

## 📊 4. Data Organization
The dataset contains **3 experimental runs**:

- **Run 1** → ~35 days, ended in **bearing 3 outer race fault**.  
- **Run 2** → ~7 days, ended in **bearing 3 inner race fault**.  
- **Run 3** → ~7 days, ended in **bearing 1 roller element fault**.  

Each run captures the **entire life cycle**:
- Start: Healthy condition  
- Mid: Early fault initiation  
- End: Catastrophic failure  

---

## 🧾 5. Labeling / Ground Truth
- **No per-file fault labels** are provided.  
- Only **start time** and **end of run (failure)** are known.  
- Health state must be inferred using signal features (RMS, kurtosis, frequency domain).  

---

## 🔍 6. Fault Progression Characteristics
- **Early Stage**: Low vibration, noise-like signals, weak fault frequencies.  
- **Mid Stage**: Fault characteristic frequencies (BPFI, BPFO, BSF) appear with harmonics.  
- **Late Stage**: Broadband high-frequency energy, RMS growth, stronger impulses.  
- **Failure**: Strong bursts, wide spectrum energy, catastrophic breakdown.  

---

## 📌 7. Features Used in Research
Common extracted features include:
- **Time Domain**: RMS, standard deviation, skewness, kurtosis, peak-to-peak.  
- **Frequency Domain**: FFT peaks at BPFI, BPFO, BSF.  
- **Time-Frequency**: Wavelet transform, spectrograms.  
- **Statistical Indicators**: Crest factor, entropy, energy ratios.  

---

## 🚀 8. Applications
- **Fault Diagnosis** (inner race, outer race, ball faults).  
- **Prognostics** (Remaining Useful Life prediction).  
- **Deep Learning** (CNN, LSTM, Transformer models for time-series classification).  
- **Feature Engineering Benchmark** for signal processing methods.  

---

## 📝 Summary Table

| Characteristic      | Details |
|---------------------|---------|
| **Bearings**        | 4 Rexnord ZA-2115 |
| **Load**            | 6000 lbs radial |
| **Speed**           | ~2000 rpm |
| **Sampling Rate**   | 20 kHz |
| **Acquisition**     | 1 sec every 10 min |
| **Sensors**         | Accelerometers |
| **Runs**            | 3 (Outer race, Inner race, Ball fault) |
| **Format**          | .mat files |
| **Labels**          | Only start/stop (no per-file labels) |
| **Use**             | Diagnostics & Prognostics |

---

## 📌 Notes
- Outer race faults → **fixed-frequency patterns** (stationary component).  
- Inner race & ball faults → **modulated patterns** (rotating components).  
- Combined faults → require **advanced signal decomposition** (FFT, Wavelets, EMD).  

---
