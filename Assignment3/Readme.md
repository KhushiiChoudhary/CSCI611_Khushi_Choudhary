Assignment 3: Small Object Detection Using YOLO

Overview
This assignment fine-tunes YOLOv8 to detect traffic signs and traffic lights from street images and video. I evaluated the pre-trained model as a baseline, then ran three training experiments with different configurations to improve small object detection performance.
Best result: mAP@0.5 of 0.9696 (Experiment 3), up from 0.0 on the pre-trained baseline.

Dataset
Traffic Sign Recognition by kuliahelektro on Roboflow Universe
Link: https://universe.roboflow.com/kuliahelektro/traffic-sign-recognition-hztr5

1,994 images | 20 classes | Pre-annotated in YOLO format
Split: 1,307 train / 458 validation / 229 test


How to Run
Option 1: Google Colab (recommended)

Open CSCI611_Assignment3_YOLO.ipynb in Google Colab
Set runtime to GPU: Runtime → Change runtime type → T4 GPU
Run all cells top to bottom — the notebook handles everything including dataset download, training, evaluation, and video inference

Option 2: Local
bashpip install ultralytics roboflow opencv-python matplotlib pandas numpy
jupyter notebook CSCI611_Assignment3_YOLO.ipynb
Note: Training without a GPU will be very slow. Google Colab is strongly recommended.

Experiments
ConfigurationmAP@0.5PrecisionRecallBaseline (pre-trained, no fine-tuning)0.00000.00000.0000Exp 1: imgsz=640, epochs=300.96360.93680.9296Exp 2: imgsz=1280, epochs=300.95990.95810.9102Exp 3: imgsz=640, epochs=50 + augmentation0.96960.95060.9327

Files
FileDescriptionCSCI611_Assignment3_YOLO.ipynbMain notebook — all code end to endbest_finetuned_model.ptBest trained model weights (Experiment 3)CSCI611_A3_Report_KhushiChoudhary.pdfWritten reportresults_comparison.csvMetrics for all experimentsperformance_comparison.pngBar chart comparing all modelsdetection_comparison.pngSide-by-side: pre-trained vs fine-tuned detectionsbaseline_detections.pngPre-trained model output on test imagesconfidence_threshold_analysis.pngEffect of conf threshold on detectionsvideo_sample_detections.pngDetections on Chico street video footagesample_dataset_images.pngSample images from the training setannotated_samples.pngLabeled dataset samples with bounding boxes

Video Inference
The best model was tested on a 30-second GoPro clip from Chico streets (GX011164.MP4).
Results at conf=0.5: 61 total detections across 900 frames — green_light (56), do_not_turn_l (3), ped_zebra_cross (2).
