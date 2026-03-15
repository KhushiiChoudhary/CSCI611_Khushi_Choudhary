# Assignment 3: Small Object Detection Using YOLO
**CSCI 611 — Spring 2026 | Khushi Choudhary | CSU Chico**

## Overview
This assignment fine-tunes YOLOv8 to detect traffic signs and traffic lights from street images and video. I evaluated the pre-trained model as a baseline, then ran three training experiments with different configurations to improve small object detection performance.

**Best result:** mAP@0.5 of 0.9696 (Experiment 3), up from 0.0 on the pre-trained baseline.

---

## Dataset
**Traffic Sign Recognition** by kuliahelektro on Roboflow Universe  
Link: https://universe.roboflow.com/kuliahelektro/traffic-sign-recognition-hztr5

- 1,994 images | 20 classes | Pre-annotated in YOLO format
- Split: 1,307 train / 458 validation / 229 test

---

## How to Run

### Option 1: Google Colab (recommended)
1. Open `CSCI611_Assignment3_YOLO.ipynb` in Google Colab
2. Set runtime to GPU: **Runtime → Change runtime type → T4 GPU**
3. Run all cells top to bottom — the notebook handles everything including dataset download, training, evaluation, and video inference

### Option 2: Local
```bash
pip install ultralytics roboflow opencv-python matplotlib pandas numpy
jupyter notebook CSCI611_Assignment3_YOLO.ipynb
```
Note: Training without a GPU will be very slow. Google Colab is strongly recommended.

---

## Experiments

| Configuration | mAP@0.5 | Precision | Recall |
|---|---|---|---|
| Baseline (pre-trained, no fine-tuning) | 0.0000 | 0.0000 | 0.0000 |
| Exp 1: imgsz=640, epochs=30 | 0.9636 | 0.9368 | 0.9296 |
| Exp 2: imgsz=1280, epochs=30 | 0.9599 | 0.9581 | 0.9102 |
| Exp 3: imgsz=640, epochs=50 + augmentation | **0.9696** | 0.9506 | 0.9327 |

---

## Files

| File | Description |
|---|---|
| `CSCI611_Assignment3_YOLO.ipynb` | Main notebook — all code end to end |
| `best_finetuned_model.pt` | Best trained model weights (Experiment 3) |
| `CSCI611_A3_Report_KhushiChoudhary.pdf` | Written report |
| `results_comparison.csv` | Metrics for all experiments |
| `performance_comparison.png` | Bar chart comparing all models |
| `detection_comparison.png` | Side-by-side: pre-trained vs fine-tuned detections |
| `baseline_detections.png` | Pre-trained model output on test images |
| `confidence_threshold_analysis.png` | Effect of conf threshold on detections |
| `video_sample_detections.png` | Detections on Chico street video footage |
| `sample_dataset_images.png` | Sample images from the training set |
| `annotated_samples.png` | Labeled dataset samples with bounding boxes |

---

## Video Inference
The best model was tested on a 30-second GoPro clip from Chico streets (GX011164.MP4).  
Results at conf=0.5: **61 total detections** across 900 frames — green_light (56), do_not_turn_l (3), ped_zebra_cross (2).
