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
