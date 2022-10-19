# Source code of Modeling Subjective Affect Annotations with Multi-Task Learning. (The Code Follows MIT License)

To read the paper: Hassan Hayat, Carles Ventura, Agata Lapedriza, “Modeling Subjective Affect Annotations with Multi-Task Learning”, Sensors. 2022; 22(14):5245. DOI: https://doi.org/10.3390/s22145245)

This package was developed by Mr.Hassan Hayat (hhassan0@uoc.edu). Please feel free to contact in case of any query regarding the package. You can run this package at your own risk. This package is free for academic use.

**Operating System**
- Ubuntu Linux

**Requirements**
- Python3.x.x
- GPU with CUDA support
- Audio features: [VGGish](https://github.com/tensorflow/models/tree/master/research/audioset/vggish)
- Visual features: [I3D Model](https://github.com/deepmind/kinetics-i3d)
- Textual features: [BERT-Base](https://github.com/google-research/bert)
- Tensorflow1.14 

**Datasets**
- [COGNIMUSE](https://cognimuse.cs.ntua.gr/research_datasets) 
- [IEMOCAP](https://sail.usc.edu/iemocap/) 
- [SemEval_2007](https://web.eecs.umich.edu/~mihalcea/affectivetext/)

## Dataset Preprocessing ##
**COGNIMUSE Dataset**

  - How to create movie clips of the COGNIMUSE dataset?

    The subtitle information of movies is provided with the timestamps. These timestamps represent the starting and ending frame information in which the     subtitle appears. We used these timestamps to create clips.

  - How to get the visual features?
    
    We used an I3D model to get the visual features. The output of the ‘Mixed-5c’ layer of the model presents the visual representation of the given         frame. Each frame was transformed into 224x224 sizes before feeding into the model.

**IEMOCAP Dataset**

  - How to get the audio features?

    The dyadic conversations are divided into 5 different sessions. VGGish pre-trained model is used to get the audio features of each utterance. The         output of the last convolutional layer presents the audio representation of the given utterance. For more details, please consult the paper. 

**SemEval_2007 Dataset**

  - How to get the textual features?

    The BERT-Base model is used to get the textual semantics of each news headline in the data. The output of the last head, i.e. 12 presents the textual     representation of the given news headline. For more details, please consult the paper.


## Setup
**Single-Task (ST) Learning using Multi-Modalities**

*Train, Validate, and Test the single-task learning using multi-modalities*

- ./st_main.py

**Multi-Task (MT) Learning using Multi-Modalities**

*Train, Validate, and Test the multi-task learning using multi-modalities*

- ./mt_main.py



