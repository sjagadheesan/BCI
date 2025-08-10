# Brain-Computer Interface (BCI) - Blink Controlled Navigation

## 📌 Overview
This project implements a **MATLAB-based Brain-Computer Interface (BCI)** that detects **eye blinks** from EEG signals captured using a **NeuroSky MindWave / ThinkGear headset** and sends movement commands via **HC-05 Bluetooth** to an external device (e.g., a robot or wheelchair).

The system provides a **Graphical User Interface (GUI)** for visual feedback and allows the user to navigate by blinking to select **Forward**, **Backward**, **Left**, or **Right** commands.

---

## 🎯 Features
- **EEG Blink Detection** using ThinkGear API
- **MATLAB GUI** to display directional options
- **HC-05 Bluetooth Communication** with external devices
- **Visual Cues** to prompt the user to blink for a selection
- **Audible Feedback** when a blink is detected
- Supports **multiple navigation cycles** in a single session

---

## 🛠️ Hardware Requirements
- **NeuroSky MindWave** or other ThinkGear-compatible EEG headset
- **HC-05 Bluetooth Module**
- Device capable of receiving movement commands (robot, wheelchair, etc.)
- Windows PC with MATLAB installed
- USB Bluetooth Adapter (if not built-in)

---

## 💻 Software Requirements
- **MATLAB** (R2017a or later recommended)
- **ThinkGear.dll** (ThinkGear API library)
- Image assets:
  - `forward.jpg`, `forwardc.jpg`, `forwards.jpg`
  - `backward.jpg`, `backwardc.jpg`, `backwards.jpg`
  - `left.jpg`, `leftc.jpg`, `lefts.jpg`
  - `right.jpg`, `rightc.jpg`, `rights.jpg`
- Proper COM port setup for the HC-05 Bluetooth module

---

## ⚙️ How It Works
1. **Initialization**
   - Connect to HC-05 Bluetooth module
   - Load GUI with directional images
   - Wait for ThinkGear headset to initialize

2. **Navigation Loop**
   - Display one direction at a time (Forward → Right → Backward → Left)
   - Prompt user to blink if they wish to select that direction
   - Detect blink from EEG signal:
     - If blink detected: send corresponding command (`F`, `R`, `B`, `L`) via Bluetooth
     - Update GUI to show selection confirmation
   - Repeat for a set number of cycles

3. **Commands Sent via Bluetooth**
   - `F` → Forward  
   - `B` → Backward  
   - `L` → Left  
   - `R` → Right  
   - `S` → Stop

---

## ▶️ Usage Instructions
1. **Setup Hardware**
   - Pair the HC-05 Bluetooth module with your PC
   - Connect the EEG headset and ensure ThinkGear drivers are installed

2. **Run the MATLAB Code**
   - Place all `.m` files, `Thinkgear.dll`, and image assets in the same folder
   - Open `guidemo.m` in MATLAB
   - Run the file

3. **Follow On-Screen Prompts**
   - Wait for initialization
   - Blink when your desired direction is highlighted
   - The connected device will move accordingly

---

## 📜 License
This project is for **educational and research purposes**.  
Ensure safety precautions when controlling physical devices.

---

## 🙌 Acknowledgements
- **NeuroSky ThinkGear API** for EEG signal acquisition
- MATLAB GUIDE for GUI development
- Bluetooth HC-05 for wireless communication
