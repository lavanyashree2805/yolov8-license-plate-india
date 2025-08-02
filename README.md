# Automatic Number Plate Detection for Indian Vehicles using YOLOv8

This project implements a two-stage vehicle and license plate detection pipeline designed specifically for Indian vehicles. It leverages the YOLOv8 object detection framework to address challenges posed by non-standardized license plate formats commonly seen across India. The system is intended for applications such as traffic monitoring, automated toll collection, and surveillance.

---

## Pipeline Overview

The detection pipeline is divided into two stages:

1. **Vehicle Detection**: Identifies and localizes vehicles (cars, bikes, trucks, and buses) using a pretrained YOLOv8 model.
2. **Number Plate Detection**: Processes the cropped vehicle images to identify and extract license plates using a custom-trained YOLOv8 model.

### Sample Output

| Description         | Image |
|---------------------|-------|
| Original Input      | ![Original](https://github.com/lavanyashree2805/yolov8-license-plate-india/blob/main/data/sample_images/step1_original.png?raw=true) |
| Cropped Vehicle     | ![Vehicle](https://github.com/lavanyashree2805/yolov8-license-plate-india/blob/main/data/sample_images/step2_cropped_vehicle.png?raw=true) |
| Cropped Number Plate| ![Plate](https://github.com/lavanyashree2805/yolov8-license-plate-india/blob/main/data/sample_images/step3_cropped_numberPlate.png?raw=true) |


---

## Model Details

- **Vehicle Detection Model**: YOLOv8n pretrained on the COCO dataset.
- **Number Plate Detection Model**: YOLOv8 trained on a subset of the Large License Plate Dataset and custom annotated images.
- **Performance**: Achieved approximately 94.5% accuracy over a test set of 10,000 images with `.xml` annotations.

---

## Getting Started
## Repository Structure


```bash
git clone https://github.com/yourusername/indian-anpr-yolov8.git
cd indian-anpr-yolov8
pip install -r requirements.txt
python inference_pipeline.py --image data/sample_images/step1_original.png
.
├── inference_pipeline.py
├── pipeline_demo.ipynb
├── requirements.txt
├── yolov8_plate_detect/
│   └── model_weights/
│       └── Lavanya_NamePlateModel.pt
├── data/
│   └── sample_images/
│       ├── step1_original.png
│       ├── step2_cropped_vehicle.png
│       └── step3_cropped_numberPlate.png
```
## Dataset Sources and References

The following datasets and resources were referenced and/or used during model training, experimentation, and fine-tuning:

1. **Car License Plate Detection Dataset – Kaggle**  
   https://www.kaggle.com/datasets/andrewmvd/car-plate-detection

2. **Indian License Plate Dataset – Kaggle**  
   https://www.kaggle.com/datasets/sanjanaprasad/indian-license-plate-dataset

3. **Electric Vehicle Number Plate Detection – Kaggle**  
   https://www.kaggle.com/datasets/dataclusterlabs/electric-vehicle-number-plate-image-dataset

4. **Indian License Plates with Labels – Kaggle**  
   https://www.kaggle.com/datasets/kedarsai/indian-license-plates-with-labels

5. **License Plate Detection Dataset ANPR (YOLO Format)**  
   https://www.kaggle.com/datasets/harshitsingh09/license-plate-detection-dataset-anpr-yolo-format

6. **Large License Plate Detection Dataset – Kaggle**  
   https://www.kaggle.com/datasets/fareselmenshawii/large-license-plate-dataset

7. **YOLOv4: Optimal Speed and Accuracy of Object Detection – ArXiv**  
   Bochkovskiy, Alexey, et al. https://arxiv.org/abs/2004.10934

8. **YOLOv5 and YOLOv8 by Ultralytics**  
   - YOLOv5: https://github.com/ultralytics/yolov5  
   - YOLOv8: https://github.com/ultralytics/ultralytics


## Future Improvements
Add OCR module to extract alphanumeric content from detected plates

Extend support for live video streams or webcam feeds

Improve robustness under poor lighting and varied angles
## License
This project is licensed under the MIT License.

## Author
Lavanya Shree

Developed at the Centre for Development of Telematics (C-DOT), New Delhi.


