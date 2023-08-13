# RootNet: Accurate Root Detection in OPG Dental Images Using YOLOv5

RootNet is an innovative project that focuses on accurate root detection in Orthopantomogram (OPG) dental images utilizing the state-of-the-art YOLOv5 algorithm. This repository showcases the successful implementation of RootNet, which involves the engineering of a custom dataset and the fine-tuning of the YOLOv5 model to achieve precise root localization.

Additionally, RootNet goes beyond root detection. It plays a pivotal role in determining the need for endodontic surgery in private dental practice. By accurately identifying and localizing dental roots, RootNet aids in identifying complex cases where endodontic surgery might be necessary.

## Project Highlights

- **Advanced Computer Vision Techniques**: RootNet leverages cutting-edge computer vision techniques to address the challenging task of root detection in complex OPG dental images.

- **YOLOv5 Algorithm Integration**: The YOLOv5 algorithm, known for its state-of-the-art performance, powers RootNet's real-time object detection capabilities, enabling efficient and accurate root localization in a single pass through the image.

- **Custom Dataset Creation**: To train the RootNet model effectively, a custom dataset was curated. This dataset was carefully annotated to include accurate root annotations, ensuring the model's robust performance.

- **Model Optimization**: The YOLOv5 model was fine-tuned using the custom dataset, resulting in a highly optimized network capable of accurately identifying and localizing dental roots in OPG images.

- **Endodontic Surgery Need Assessment**: In addition to root detection, RootNet is designed to assist in assessing the need for endodontic surgery in private dental practice. The model's accurate localization of roots aids in identifying cases that might require surgical intervention.

## Getting Started

To get started with RootNet and explore its functionalities, follow these steps:

1. **Clone the Repository**:
<details open>
<summary>Install</summary>

Clone repo and install [requirements.txt](https://github.com/mohamad-tohidi/RootNet/requirements.txt) in a
[**Python>=3.8.0**](https://www.python.org/) environment, including
[**PyTorch>=1.8**](https://pytorch.org/get-started/locally/).

```bash
git clone https://github.com/mohamad-tohidi/RootNet  # clone
cd RootNet
pip install -r requirements.txt  # install
```


2. **Prerequisites**: Ensure you have the necessary dependencies installed. You might need Python, the YOLOv5 framework, and other packages mentioned in the repository's requirements.

3. **Dataset**: If you wish to train the model with your own dataset, follow the guidelines in the `dataset/README.md` file for dataset preparation and annotations.

4. **Model Training**: Refer to `training/README.md` for instructions on how to train the RootNet model using the prepared dataset.

5. **Inference**: Once the model is trained, you can perform root detection and endodontic surgery need assessment on OPG images using the inference scripts provided in the `inference/` directory.

## Contributing

Contributions to RootNet are welcomed! Whether you want to improve the dataset, enhance the model architecture, or optimize the code, your input is valuable. Please refer to `CONTRIBUTING.md` for guidelines on how to contribute to this project.

## License

RootNet is distributed under the [MIT License](LICENSE). Feel free to use, modify, and distribute the code in accordance with the license terms.

## Acknowledgments

We extend our gratitude to the open-source community, the authors of YOLOv5, and the contributors who have helped make this project possible.

---

By Mohammad Tohidi

feel free to contact: the.mohammad.tohid@gmail.com





<div align="center">
  <a href="https://ultralytics.com/yolov8" target="_blank">
  <img width="100%" src="https://raw.githubusercontent.com/ultralytics/assets/main/yolov8/yolo-comparison-plots.png"></a>
</div>


</details>

<details>
<summary>Inference</summary>

```python
import torch

# Model
model = torch.hub.load("ultralytics/yolov5", "RootNet-Weights")  # or other weights 

# Images
img = "opg.jpg"  # or file, Path, PIL, OpenCV, numpy, list

# Inference
results = model(img)

# Results
results.print()  # or .show(), .save(), .crop(), .pandas(), etc.
```

</details>

<details>
<summary>Inference with detect.py</summary>

`detect.py` runs inference on a variety of sources, downloading [models](https://github.com/ultralytics/yolov5/tree/master/models) automatically from
the latest YOLOv5 [release](https://github.com/ultralytics/yolov5/releases) and saving results to `runs/detect`.

```bash
python detect.py --weights RootNet-Weights.pt --source 0                               # webcam
                                               img.jpg                         # image
                                               vid.mp4                         # video
                                               screen                          # screenshot
                                               path/                           # directory
                                               list.txt                        # list of images
                                               list.streams                    # list of streams
                                               'path/*.jpg'                    # glob
                                               'https://youtu.be/Zgi9g1ksQHc'  # YouTube
                                               'rtsp://example.com/media.mp4'  # RTSP, RTMP, HTTP stream
```





