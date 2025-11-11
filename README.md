# FCE-YOLOv8: Tea Leaf Disease Detection
## 🚀 Highlights

- ✅ Baseline: YOLOv8-m achieves 98.25% mAP\@0.5.
- ✅ Enhanced with Global Context (GC) attention block ➝ improves mAP\@0.5 to 98.33%.
- ✅ CBAM integration (YOLOv8-ResCBAM) ➝ highest recall (96.03%).
- ✅ Dataset: 7,000 images, 7 classes (tea leaf diseases + pests + healthy).

## 📊 Performance Summary

| Model              | Precision | Recall | mAP\@0.5   | mAP\@0.5:0.95 |
| ------------------ | --------- | ------ | ---------- | ------------- |
| YOLOv8m (Baseline) | 95.39%    | 95.72% | 98.25%     | 80.74%        |
| YOLOv8-ResCBAM     | 93.95%    | 96.03% | 98.05%     | 78.72%        |
| YOLOv8+GC          | 95.09%    | 94.52% | **98.33%** | 76.84%        |

## 🧠 Dataset Details

- **Source**: Roboflow Universe
- **Classes (7 total)**:
  - Black Rot
  - Brown Blight
  - Leaf Rust
  - White Scab
  - Tea Mosquito Bug
  - Red Spider Mite
  - Healthy
- **Split**: Train 80% / Val 10% / Test 10%
- **Format**: Annotated with bounding boxes.

## 🧪 Training Configuration

- Framework: Ultralytics YOLOv8 (open-source)
- Model: `yolov8m` (with/without GC, ResCBAM)
- Image size: 640×640
- Epochs: 200
- Batch size: 8
- Optimizer: default SGD (YOLOv8 config)

## 📦 Installation

```bash
pip install -r requirements.txt
```

## 🧬 Training & Inference

```bash
# Training YOLOv8 + GC
yolo task=detect mode=train model=yolov8m.yaml data=tea.yaml epochs=200 imgsz=640

# Inference
yolo task=detect mode=predict model=best.pt source=path/to/images
```

## 📸 Visualization

- GC improves detection of **Tea Mosquito Bug**.
- ResCBAM highlights subtle patterns and increases **recall**.
- YOLOv8+GC shows wider context boxes for fine patterns.

## 📚 Citation

Please cite the corresponding paper when using this code or dataset.

## 🔗 References

1. Soeb et al. (2023). Tea leaf detection using YOLOv7. *Scientific Reports*
2. Alhwaiti et al. (2025). YOLO for Plant Disease Identification. *Scientific Reports*
3. Xue et al. (2023). YOLO-Tea. *Forests*
4. Yang et al. (2020). GC-YOLOv3. *Electronics*
5. Cao et al. (2019). GCNet. *ICCV Workshops*
6. Ju et al. (2024a). YOLOv8+GC. *ISPACS*
7. Ju et al. (2024b). YOLOv8-ResCBAM. *ICONIP*
8. Roboflow (2023). [https://roboflow.com/model/yolov8](https://roboflow.com/model/yolov8)
9. Ruiyang Ju GitHub: [https://github.com/RuiyangJu](https://github.com/RuiyangJu)

## 🙌 Acknowledgments

Thanks to Ultralytics for YOLOv8 and Roboflow for dataset tools.

---

> This repository demonstrates how lightweight attention modules can boost disease detection in precision agriculture. Perfect for drones, mobile devices, and real-time applications. 🌿
