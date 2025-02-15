# Modeling Subjective Affect Annotations with Multi-Task Learning  
*(Code Licensed under the MIT License)*

For further details, please refer to the paper:  
**Hassan Hayat, Carles Ventura, Agata Lapedriza, “Modeling Subjective Affect Annotations with Multi-Task Learning”, Sensors, 2022, 22(14):5245. DOI: [10.3390/s22145245](https://doi.org/10.3390/s22145245)**

This package was developed by Mr. Hassan Hayat (hhassan0@uoc.edu). For any inquiries regarding this package, please feel free to contact him. The package is provided free for academic use and is distributed at your own risk.

---

## Operating System

- **Ubuntu Linux**

---

## Requirements

- **Python:** 3.x.x  
- **GPU:** With CUDA support  
- **Audio Features:** [VGGish](https://github.com/tensorflow/models/tree/master/research/audioset/vggish)  
- **Visual Features:** [I3D Model](https://github.com/deepmind/kinetics-i3d)  
- **Textual Features:** [BERT-Base](https://github.com/google-research/bert)  
- **TensorFlow:** 1.14

---

## Datasets

- [COGNIMUSE](https://cognimuse.cs.ntua.gr/research_datasets)  
- [IEMOCAP](https://sail.usc.edu/iemocap/)  
- [SemEval_2007](https://web.eecs.umich.edu/~mihalcea/affectivetext/)

---

## Dataset Preprocessing

### COGNIMUSE Dataset

- **Movie Clips Creation:**  
  The COGNIMUSE dataset provides subtitle information with timestamps that indicate the start and end frames where a subtitle appears. These timestamps are used to create movie clips.

- **Visual Feature Extraction:**  
  An I3D model is used to extract visual features. The output from the **'Mixed-5c'** layer of the model represents the visual features of each frame. Prior to feeding the frames into the model, each frame is resized to **224x224** pixels.

### IEMOCAP Dataset

- **Audio Feature Extraction:**  
  The dataset’s dyadic conversations are divided into five sessions. A pre-trained VGGish model is used to extract audio features for each utterance. The audio representation is taken from the output of the last convolutional layer. Please refer to the paper for further details.

### SemEval_2007 Dataset

- **Textual Feature Extraction:**  
  The BERT-Base model is employed to obtain textual semantics for each news headline. The representation is derived from the final layer (i.e., the 12th layer) of the model. Please refer to the paper for more details.

---

## Setup Instructions

### Single-Task (ST) Learning using Multi-Modalities

To train, validate, and test using multi-modalities in a single-task setting, execute the following:

```bash
./st_main.py
```

### Multi-Task (MT) Learning using Multi-Modalities

To train, validate, and test using multi-modalities in a multi-task setting, execute the following:

```bash
./mt_main.py
```
