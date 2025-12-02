# SmartWeed – Automated Weed Detection and Removal (Edge AI + Robotics)

## 1. Why it is built

SmartWeed is built to solve the problem of **manual, labor-intensive weed removal** in agriculture.  
Traditional weeding is:
- Slow and tiring for farmers  
- Often dependent on chemical herbicides  
- Hard to scale for large fields  

The goal is to:
- **Reduce manual effort**
- **Minimize chemical usage**
- **Make weed control more precise and sustainable** using technology.

---

## 2. How it is built

SmartWeed is implemented as a combination of **Edge AI + embedded hardware + simple robotics**:

- **Edge AI:**  
  - A camera captures images of the crop row.  
  - A trained **YOLO-based object detection model** runs on an **NVIDIA Jetson Xavier NX** to detect weeds in real time.

- **Hardware & Control:**  
  - Jetson Xavier NX mounted on a carrier board with a CSI camera.  
  - An **ESP32 microcontroller** controls a **linear actuator(2D linear stage)**.  
  - When the AI model detects a weed in a target region, a signal is sent from the Jetson to the ESP32, which triggers the actuator.

- **Power & Integration:**  
  - Powered by a **24V battery** with DC-DC converters for different components.  
  - Designed to be mounted on a small mobile platform that can move along crop rows.

Only a **minimal overview and high-level structure** are shared here. Full datasets, training notebooks, and detailed hardware code are kept private.

---

## 3. What it does

- Scans crop rows using a camera in front of the plants.  
- **Detects weeds in real time** using the on-board AI model.  
- Sends a trigger to the actuator system when a weed is found in the defined zone.  
- The actuator then performs a **targeted mechanical action** to remove or disturb the weed.



  ## 4. Tech Stack

- **Edge AI:** YOLO (custom-trained), PyTorch
- **Hardware:** NVIDIA Jetson Xavier NX, ESP32
- **Mechanism:** Custom 2D linear stage (X–Y motion)
- **Power:** 24V Li-ion battery with DC-DC converters
- **Tools Used:** Google Colab (training), Ubuntu/Linux, Serial communication




## 5. My Contribution

- Designed the end-to-end system architecture (AI + hardware + motion control)
- Captured and prepared the custom weed dataset (YOLO format)
- Trained the YOLO model for real-time weed classification
- Implemented the inference pipeline on the Jetson Xavier NX
- Developed the ESP32-based control logic for the 2D linear stage
- Integrated the hardware, motion mechanism, and AI model into a working prototype


In simple words:  
> SmartWeed looks at the field, recognizes weeds using AI, and activates a mechanism to remove them automatically.
