# 🦴 Bone Fracture Detection (YOLOv8)

An end-to-end **computer vision project** for detecting bone fractures in X-ray images using **YOLOv8**, trained on multiple fracture datasets and deployed with a **Gradio web interface**.

> ⚠️ For **educational and research purposes only**. Not a medical diagnostic tool.

---

## 🚀 Features

* YOLOv8-based fracture detection
* Bounding box localization on X-ray images
* Merged fracture detection datasets
* Model evaluation using mAP metrics
* Interactive Gradio web interface

---

## 🗂️ Dataset

The model is trained using **fracture detection datasets only**:

* **FracAtlas** (JSON annotations)
* **Bone Fracture Detection datasets** (YOLO format)

All datasets are converted to a **unified YOLO format**.

```
combined_bone/
 ├── images/{train,val,test}
 └── labels/{train,val,test}
```

---

## 🧠 Model

* **Architecture:** YOLOv8n (Nano)
* **Task:** Object Detection
* **Classes:** 1 (`fracture`)
* **Input Size:** 640 × 640

YOLOv8 is chosen for its **speed–accuracy balance**, suitable for medical imaging tasks.

---

## ⚙️ Training

```python
model.train(
    data="combined.yaml",
    epochs=50,
    imgsz=640,
    batch=16
)
```

---

## 📊 Evaluation

The model is evaluated on a **held-out test set** using:

* mAP@50
* mAP@50–95
* Precision & Recall

Typical results:

* **mAP@50:** 0.60 – 0.75

---

## 🌐 Gradio Interface

The project includes a **Gradio-based UI** that allows:

* Uploading X-ray images
* Adjusting confidence threshold
* Viewing detected fracture regions

Run locally or in Colab:

```python
interface.launch(share=True)
```

---

## 🔮 Future Work

* Multi-class fracture detection
* Severity estimation
* Larger YOLO models (YOLOv8s/m)
* Clinical system integration



