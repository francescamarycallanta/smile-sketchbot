# smile-sketchbot
The Smile SketchBot uses a Raspberry Pi and OpenCV to detect smiles in real time, then processes images with Python and NumPy. Processing 4 generates G-code, which a modified Ender 3 V2 draws using a pen. This blends computer vision, creative coding, and digital fabrication.

<img src="assets/demo_sketchbot.gif" alt="Smile SketchBot Demo" width="500"/>

---

## 🌟 Features
- Real-time **smile detection** using **OpenCV Haar Cascades**.  
- Converts faces into **high-contrast sketches** with Canny edge detection.  
- Generates **G-code** with **Processing 4** to control the printer.  
- Modified **Ender 3 V2** prints drawings with a **pen holder** on a whiteboard.  
- ~95% smile detection accuracy under various lighting conditions.  
- Potential for use in **interactive art**, **AI-assisted learning**, and **therapeutic observation**.

---

## 🛠 Tech Stack

| Category            | Tools & Software |
|--------------------|------------------|
| **Hardware**       | Raspberry Pi 4, Ender 3 V2 (modded), Logitech camera |
| **Computer Vision**| Python, OpenCV, NumPy |
| **Image Processing** | Canny edge detection |
| **G-code Generation** | Processing 4 |
| **Visualization** | Matplotlib |
| **Communication** | USB Serial between Raspberry Pi and printer |

---

## ⚙️ How It Works
1. **Smile Detection**  
   - Raspberry Pi captures live video feed.  
   - **OpenCV Haar Cascades** detect face, eyes, and smile.

2. **Image Processing**  
   - Snapshot captured when a smile is detected.  
   - Converted to grayscale → **Canny edge detection** → resized/cropped.

3. **G-code Generation**  
   - Processed image split into a grid.  
   - Brightness values → waveform patterns → translated into **G-code** using **Processing 4**.

4. **Drawing Execution**  
   - G-code sent to a **modified Ender 3 V2** with a pen holder.  
   - Printer recreates the portrait on a mounted whiteboard.

---

## 📐 System Architecture
```mermaid
flowchart LR
  Cam[Camera Input] --> Pi[Raspberry Pi + Python]
  Pi -->|Smile Detection + Canny Edges| Process[Processing 4]
  Process -->|G-code| Printer[Ender 3 V2 (Pen Holder)]
  Printer --> Output[Whiteboard Drawing]
