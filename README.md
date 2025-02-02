# 🚁 Indoor Autonomous Drone

Welcome to the **Indoor Autonomous Drone** project! This repository contains a robust drone system that leverages advanced computer vision techniques for indoor navigation, object detection, and door (ArUco marker) recognition. Whether you're running the code on a real Tello drone or simulating it in Webots, you'll enjoy a seamless blend of manual and autonomous control.

---

## 🔍 Overview

- **Real-Time Object Detection:**  
  Powered by YOLOv4, the system identifies and labels objects in the live video feed.

- **Door Detection & Approach:**  
  Using OpenCV's ArUco module, the drone detects a specific marker (ID 4) representing a door and autonomously navigates towards it.

- **Dual Deployment Modes:**  
  - **Real Drone Mode:** Control a physical Tello drone using [djitellopy](https://github.com/damiafuentes/DJITelloPy).  
  - **Simulation Mode:** Run the same control logic in Webots for development and testing.

- **State-Based Autonomous Navigation:**  
  The drone smoothly transitions through states (e.g., mapping, door approach, stopped) for reliable indoor navigation.

---

## 🚀 Features

- **YOLOv4 Integration** for robust object detection  
- **ArUco Marker Detection** to identify and approach doors  
- **Manual & Autonomous Control** modes  
- **Real Drone & Simulation Support**  
- **Emergency Stop & Safety Mechanisms**

---

## 🛠️ Requirements

- **Python 3.x**
- **Libraries:**
  - [OpenCV](https://opencv.org/) (with contrib modules)  
    ```bash
    pip install opencv-python opencv-contrib-python
    ```
  - [NumPy](https://numpy.org/)  
    ```bash
    pip install numpy
    ```
  - [djitellopy](https://github.com/damiafuentes/DJITelloPy) (for real drone mode)  
    ```bash
    pip install djitellopy
    ```
- **Additional Software:**
  - [Webots](https://cyberbotics.com/) for simulation
- **Model Files:**  
  YOLOv4 configuration (`.cfg`), weights (`.weights`), and class names (`coco.names`)
- **Optional:** Camera calibration file (e.g., `MultiMatrix.npz`)

---

## 📥 Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yazanyehya/Indoor-Autonomous-Tello-master.git
   ```
2. **Install Dependencies:**
   ```bash
   pip install opencv-python opencv-contrib-python numpy djitellopy
   ```
3. **Update File Paths:**  
   Edit the source files to point to your YOLOv4 files and camera calibration data.
4. **(For Simulation)**  
   Import the Webots simulation project and ensure all device names are configured correctly.

---

## 🎮 Usage

### Real Drone Mode

- **Script:** `drone_control.py`
- **Controls:**
  - **T**: Takeoff  
  - **L**: Land  
  - **Arrow Keys, Q/E, W/S**: Manual navigation  
  - **A/D**: Enable/Disable autonomous mode  
  - **K**: Open door  
  - **Q**: Quit
- **Run:**
   ```bash
   python drone_control.py
   ```

### Simulation Mode (Webots)

- **Script:** `simulation_control.py`
- **Controls:** Same as Real Drone Mode  
- **Run:**
  1. Launch Webots and load the simulation project.
  2. Run:
     ```bash
     python simulation_control.py
     ```

---

## 💻 Code Overview

- **`detect_objects(frame)`**  
  Performs YOLOv4-based object detection on each video frame.

- **`follow_marker(...)`**  
  Implements the state-based logic for mapping, door approach, and stopping when the ArUco marker is detected.

- **Manual & Autonomous Control:**  
  Supports both keyboard-based manual overrides and autonomous navigation modes.

---

## 🎨 Customization

- **File Paths & Settings:**  
  Update the YOLOv4 model paths and camera calibration file as needed.
- **Control Parameters:**  
  Tweak thresholds, speeds, and smoothing factors to optimize performance in your environment.
- **Marker Settings:**  
  The door detection is configured for marker ID 4 by default. Adjust if necessary.

---

## 🛠️ Troubleshooting

- **Pose Estimation Issues:**  
  Verify camera calibration and adjust marker size parameters.
- **Control Instability:**  
  Modify the smoothing factors or PID parameters.
- **Simulation Errors:**  
  Ensure Webots is properly installed and the simulation project is correctly configured.

---

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- **djitellopy:** [DJITelloPy GitHub](https://github.com/damiafuentes/DJITelloPy)
- **OpenCV:** [OpenCV.org](https://opencv.org/)
- **Webots:** [Cyberbotics Webots](https://cyberbotics.com/)
- **YOLOv4 & COCO:** For powering real-time object detection

---

Happy coding and fly safe! 🚀
```

---

This README uses emojis to add personality and clarity while keeping the content professional and easy to follow. Simply copy the content into a `README.md` file in your repository's root directory. Enjoy!
