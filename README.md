# ObjectFusion-AI-Based-Image-Synthesis-from-Selective-Object-specification

## Overview:
This project integrates state-of-the-art techniques in Natural Language Processing (NLP) and Computer Vision (CV) to perform image captioning and object segmentation based on textual descriptions from the COCO dataset. The methodology combines SpaCy for text preprocessing, ResNet for object detection, DeepLab with DenseNet201 for segmentation, and mask generation to isolate detected objects from the background. The ultimate goal is to create a cohesive visual representation where each detected object is not only identified but also segmented from the image.

## Authors:
- Mummadi Hemanth Reddy
- Okesh Ankireddypalli
- Mouhitha Arella
- Saranya Gujjula
- Suja Palaniswamy

## Table of Contents:
- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
  - [Textual Data Preprocessing with SpaCy](#textual-data-preprocessing-with-spacy)
  - [Object Detection using ResNet](#object-detection-using-resnet)
  - [Anchor Refinement](#anchor-refinement)
  - [Segmentation Using DenseNet201 and DeepLab](#segmentation-using-densenet201-and-deep-lab)
  - [Masking the Detected Objects](#masking-the-detected-objects)
  - [Combining the Segmented Objects](#combining-the-segmented-objects)
  - [Visualization and Evaluation](#visualization-and-evaluation)
- [Evaluation Metrics](#evaluation-metrics)
- [Contributing](#contributing)

## Installation
To get started, clone the repository and install the required dependencies:

1. Clone the repository:
    ```bash
    git clone https://github.com/okesh1215/ObjectFusion-AI-Based-Image-Synthesis-from-Selective-Object-specification.git
    ```

2. Navigate to the project folder:
    ```bash
    cd ObjectFusion-AI-Based-Image-Synthesis-from-Selective-Object-specification
    ```

3. Install the dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage
1. Download the COCO dataset and place it in the appropriate folder (`data/coco`).
2. Run the image captioning and object segmentation pipeline.
3. Visualize the results: The output image with segmented objects and detected bounding boxes will be saved in the `output/` directory.

## Methodology

### Textual Data Preprocessing with SpaCy
- **Tokenization**: Breaking down the sentences into tokens (words/phrases).
- **Named Entity Recognition (NER)**: Identifying objects and actions.
- **Object Extraction**: Structuring objects from the text to correspond with image regions.

### Object Detection using ResNet
- Load the ResNet model, pre-trained on the COCO dataset.
- Process the image to detect objects, represented by bounding boxes.
- Output consists of object localization and predicted labels.

### Anchor Refinement
- Refine the initial bounding boxes for more accurate object localization.
- Minimize false positives by adjusting context around detected objects.

### Segmentation Using DenseNet201 and DeepLab
- **DenseNet201**: Extract fine-grained features to ensure high accuracy.
- **DeepLab**: Perform semantic segmentation to generate precise object boundaries.
- **Segmentation Masks**: The pixel-level boundary of the detected object.

### Masking the Detected Objects
- Apply the segmentation mask to isolate the object from the background, leaving only the object of interest visible.

### Combining the Segmented Objects
- Combine segmented objects into one cohesive image, ensuring all objects are visible and correctly segmented.

### Visualization and Evaluation
- Visualize images with detected objects and segmentation masks.
- Evaluate using Intersection over Union (IoU) and pixel-wise accuracy.

## Evaluation Metrics
- **Intersection over Union (IoU)**: Measures the overlap between predicted bounding boxes and ground truth.
- **Pixel-wise accuracy**: Assesses the pixel-level accuracy of segmentation masks.

## Contributing
Feel free to contribute to this project! If you have any suggestions or improvements, open an issue or submit a pull request.

### Steps to contribute:
1. Fork the repository.
2. Create a feature branch:
    ```bash
    git checkout -b new-feature
    ```
3. Make changes and commit them:
    ```bash
    git commit -am 'Add new feature'
    ```
4. Push to the branch:
    ```bash
    git push origin new-feature
    ```
5. Open a pull request.
