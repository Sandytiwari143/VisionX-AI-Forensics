# VisionX AI: Multi-Modal CV & Generative Tamper Forensics

An industry-grade computer vision and image forensics engine designed to detect real-time objects, extract text, and uncover generative AI background manipulation (Inpainting/Generative Fill swaps).

---

## Key Capabilities

* **AI Background Swap & Inpainting Forensics:** Isolates human subjects using boundary segmentation and calculates edge seam gradients and Lab color deltas to detect synthetic background replacement with 95% confidence.
* **Error Level Analysis (ELA) & Frequency Audit:** Computes JPEG compression variance and Fast Fourier Transform (FFT) high-frequency distributions to identify digital tampering.
* **Multi-Modal Object Detection:** Real-time object identification using YOLOv8 with bounding-box confidence scores.
* **OCR Text Extraction:** Optical Character Recognition powered by EasyOCR for text parsing across visual media.
* **Interactive UI:** Built-in Gradio interface providing real-time forensic overlays, edge maps, and automated audit reports.

---

## Tech Stack

* **Core:** Python 3.10+, NumPy, OpenCV
* **Vision & Models:** YOLOv8 (Ultralytics), EasyOCR, PIL
* **Forensics:** Fast Fourier Transform (FFT), Laplacian Edge Gradient, Morphological Boundary Dilation
* **Interface & Deployment:** Gradio, FastAPI

---

## How It Works

1. **Subject Boundary Isolation:** `yolov8n-seg` extracts precise human masks down to fine contours (hair, shoulders, garments).
2. **Transition Ring Mapping:** Morphological dilation and erosion extract a 5px edge boundary band.
3. **Forensic Discrepancy Analysis:** 
   * **Seam Gradient:** Evaluates Sobel edge discontinuities along the blending seam where original pixels meet diffusion pixels.
   * **Color Delta:** Computes Lab space chrominance shift between subject and generative fill regions.

---

## Quickstart

```bash
# Clone the repository
git clone [https://github.com/Sandytiwari143/VisionX-AI-Forensics.git](https://github.com/Sandytiwari143/VisionX-AI-Forensics.git)
cd VisionX-AI-Forensics

# Install dependencies
pip install ultralytics easyocr gradio opencv-python pillow
