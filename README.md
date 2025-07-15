# Thai Crack Captioning Dataset

A domain-specific dataset for crack classification and captioning in the Thai language context.

## Data Source

The images and reports used in this dataset are derived from the [Traffy Fondue](https://bangkok.traffy.in.th) platform, an open government service for citizen-reported issues in Thailand, operated by NECTEC. Only publicly available and non-personally identifiable data were included. Please refer to the Traffy Fondue website for more information about the platform and its data policy.

## Example Notebooks

This repository includes two example Jupyter notebooks to demonstrate how to use the dataset for model training and evaluation:

- `Thai_Crack_Captioning_no_ViT.ipynb`:  
  Example pipeline for crack captioning and severity assessment **without** the Vision Transformer (ViT) encoder.

- `Thai_Crack_Captioning_with_ViT.ipynb`:  
  Example pipeline for crack captioning and severity assessment **with** the Vision Transformer (ViT) encoder.

Both notebooks provide step-by-step code for:
- Loading the dataset and annotations
- Preprocessing images and bounding box data
- Preparing captions and severity labels
- Building and training deep learning models
- Evaluating and visualizing results

These notebooks can be used as templates for further experiments or model adaptation.

## JSONL Annotation Files

Each `.jsonl` (JSON Lines) file provides detailed annotations for every image in each split (`train.jsonl`, `val.jsonl`, `test.jsonl`).  
Each line is a JSON object containing the following fields:

- `image`: Relative path to the image file (e.g., `./test/2025-ZHZF78.jpg`)
- `xml`: Relative path to the corresponding bounding box annotation file (PASCAL VOC XML; e.g., `./test/2025-ZHZF78.xml`)
- `caption`: Expert-annotated caption (in Thai), describing the crack, possible causes, and recommendations
- `severity`: Integer score (e.g., 1–3) indicating the level of damage  
- `bndbox`: Object containing bounding box coordinates (`xmin`, `ymin`, `xmax`, `ymax`) for the crack region 
- `original_size`: `[width, height]` of the original image, used for interpreting bounding box coordinates

**Example content:**
```json
{"image": "./test/2025-ZHZF78.jpg", "xml": "./test/2025-ZHZF78.xml", "caption": "เป็นการ crack ของผนังอาคาร ...", "severity": 3, "bndbox": {"xmin": 69.85, "ymin": 0.11, "xmax": 147.73, "ymax": 224.0}, "original_size": [1536, 2048]}
 
