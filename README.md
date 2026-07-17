# iranian-cars-number-plate-object-detection-with-yolo8
# 🚗 Automatic Number Plate Recognition (ANPR) with YOLOv8

An object detection project that locates vehicle license plates in images using **YOLOv8** (Ultralytics). The model is trained on a custom-labeled dataset hosted on Roboflow and can be used to detect plates in new images.

## 📌 Overview

The model takes an image of a vehicle as input and outputs a bounding box around the license plate. It's built on `yolov8n.pt` (the nano variant of YOLOv8) fine-tuned on a custom ANPR dataset.

## 🗂️ Dataset

- iranian cars number plate
https://www.kaggle.com/datasets/skhalili/iraniancarnumberplate

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Base model | `yolov8n.pt` |
| Epochs | 55 |
| Batch size | 16 |
| Image size | 416×416 |

## 📁 Repository Structure

```
.
├── README.md
├── train.py              
├── predict.py             
├── requirements.txt                    
└── results/                 
```


## 🚀 Getting Started

### 1. Install dependencies

```bash
pip install -r requirements.txt
```



### 2. Train the model

```bash
python train.py --epochs 55 --batch 16 --imgsz 416
```

This will:
1. Download the dataset into `ANPR-1/`
2. Train `yolov8n.pt` on it with the given hyperparameters
3. Save the best weights to `runs/detect/train/weights/best.pt`
4. Save training curves (F1, PR curve, confusion matrix) to `runs/detect/train/`

### 3. Run predictions on new images

```bash
python predict.py --weights runs/detect/train/weights/best.pt --source path/to/images
```

Predicted images (with bounding boxes drawn) are saved under `runs/detect/predict/`.

## 📊 Results

<!-- After training, paste a few sample metrics/images here, e.g.: -->
<!-- ![Confusion Matrix](results/confusion_matrix.png) -->
<!-- ![Sample Prediction](results/sample_prediction.jpg) -->

Fill in after training: final mAP50, mAP50-95, precision, recall, and a couple of example detections.

## 🛠️ Tech Stack

- Python
- Ultralytics YOLOv8
- Roboflow (dataset hosting/versioning)
- OpenCV, Matplotlib

## 👤 Author

Sobhan Ghanbari Gorji

## 📄 License

Released under the MIT License.

