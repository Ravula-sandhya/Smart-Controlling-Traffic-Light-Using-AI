# 🚦 Smart Control of Traffic Light Using Artificial Intelligence

An AI-powered traffic signal management system that uses **real-time vehicle detection** to dynamically adjust green light durations — replacing inefficient fixed-timer systems with intelligent, density-based control.

---

## 📌 Problem Statement

Conventional traffic lights operate on fixed timers regardless of actual traffic conditions. This leads to:

- Unnecessary waiting time on low-traffic lanes
- Congestion on high-density lanes
- Fuel wastage and increased pollution

This project solves this by using AI to **detect and count vehicles in real time** and **automatically adjust signal timings** based on lane density.

---

## 🎯 Key Results

| Metric | Fixed Timer System | This AI System |
|---|---|---|
| Avg vehicle wait time | Baseline | **~25% reduction** |
| Detection method | None | YOLOv5 + MobileNet SSD |
| Signal timing | Fixed interval | Dynamic (density-based) |
| Vehicle types detected | N/A | Car, Bus, Bicycle |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core language |
| OpenCV | Video processing & frame capture |
| YOLO (YOLOv5) | Real-time vehicle detection |
| MobileNet SSD | Single-shot vehicle detection (extension) |
| TensorFlow | Model inference for SSD detection |
| NumPy | Numerical operations |
| Tkinter | GUI interface |

---

## 📁 Project Structure

```
Smart-Controlling-Traffic-Light-Using-AI/
│
├── Main.py                  # Main GUI application entry point
├── yolo_traffic.py          # YOLO-based vehicle detection & counting
├── traffic_simulation.py    # Traffic signal simulation logic
├── yolo-coco/               # Pre-trained model files (add manually)
│   ├── MobileNetSSD_deploy.prototxt.txt
│   ├── MobileNetSSD_deploy.caffemodel
│   └── frozen_inference_graph.pb
└── Videos/                  # Sample traffic video files (add manually)
```

---

## ⚙️ How It Works

1. **Video Input** — User loads a traffic video file through the GUI
2. **Vehicle Detection** — YOLO or MobileNet SSD scans each frame and detects vehicles (cars, buses, bicycles)
3. **Density Calculation** — System counts vehicles per lane in real time
4. **Signal Control** — Green light duration is dynamically assigned — higher density lanes get more green time
5. **Simulation** — A built-in traffic simulation shows the before/after comparison

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/Ravula-sandhya/Smart-Controlling-Traffic-Light-Using-AI.git
cd Smart-Controlling-Traffic-Light-Using-AI
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Add model files
Download and place these inside a `yolo-coco/` folder:
- `MobileNetSSD_deploy.prototxt.txt`
- `MobileNetSSD_deploy.caffemodel`
- `frozen_inference_graph.pb`

> These are standard MobileNet SSD pretrained models available from the OpenCV GitHub repository.

### 4. Run the application
```bash
python Main.py
```

### 5. Using the GUI
- Click **"Run Traffic Simulation"** to see the signal timing simulation
- Click **"Run Extension Yolo Traffic Detection & Counting"** to load a video and run YOLO detection
- Click **"Run Existing Single Shot Traffic Detection"** to run MobileNet SSD detection

---

## 📦 Requirements

```
opencv-python
numpy
tensorflow
```

---

## 📊 How Signal Timing Works

```
Vehicle Count per Lane  →  Green Light Duration
─────────────────────────────────────────────
0  – 5  vehicles        →  10 seconds
6  – 15 vehicles        →  20 seconds
16 – 30 vehicles        →  35 seconds
30+     vehicles        →  50 seconds
```

Low-traffic lanes get shorter green time → high-traffic lanes get priority → overall wait time reduced.

---

## 🔮 Future Improvements

- [ ] Support for live CCTV camera feed instead of video files
- [ ] Multi-junction coordination across intersections
- [ ] Emergency vehicle detection and priority override
- [ ] Web dashboard for real-time monitoring

---

## 👩‍💻 Author

**Sandhya Ravula**
- GitHub: [@Ravula-sandhya](https://github.com/Ravula-sandhya)
- LinkedIn: [linkedin.com/in/sandhya-ravula](https://linkedin.com/in/sandhya-ravula)
- Email: ravulasandhya45@gmail.com

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
