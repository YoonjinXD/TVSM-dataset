# TVSM Dataset

The TV Speech and Music (TVSM) dataset contains speech and music activity labels across a variety of TV shows and their corresponding audio features extracted from professionally-produced high-quality audio. 
The dataset aims to facilitate research on speech and music detection tasks. 


## Get the dataset

- The dataset can be downloaded via Zenodo.org [The dataset Will be released on Sep 13 (sorry it's still under processing!). Please come back later!].
- The paper can be downloaded via [EURASIP open access](https://asmp-eurasipjournals.springeropen.com/articles/10.1186/s13636-022-00253-8).
- This repo contains materials and codebase to reproduce the baseline experiment in the paper.

## License and attribution
```
@article{Hung2022,
  title={{A Large TV Dataset for Speech and Music Activity Detection},
  author={Hung, Yun-Ning and Wu, Chih-Wei and Orife, Iroro and Hipple, Aaron and Wolcott, William and Lerch, Alexander},
  journal={EURASIP Journal on Audio, Speech, and Music Processing},
  volume={2022},
  number={1},
  pages={21},
  year={2022},
  publisher={Springer}
}
```
The TVSM dataset is licensed under a [Apache License 2.0 license](https://www.apache.org/licenses/LICENSE-2.0) 

## Dataset introduction

The downloaded dataset has the following structure:
```
└─── READEME.txt
└─── TVSM-cuesheet/
│    └─── labels/
│    └─── mel_features/
│    └─── mfcc/
│    └─── vgg_features/
│    └─── TVSM-xxxx_metadata.csv
└─── TVSM-pseudo/
└─── TVSM-test/
```

- **READEME.txt**: basic information about the dataset
- **TVSM-cuesheet/**: smaller subset used for training. The labels are derived from cuesheet information
- **TVSM-pseudo/**: larger subset used for training. The labels are labeled from a pre-trained model trained on TVSM-cuesheet
- **TVSM-test/**: subset for testing. The labels are labeled by human annotators

Each subset folder has the same structure:
- **labels/**: speech and music activation labels for each sample. Each row in a csv file represents "start time", "end time" and "s(speech)/m(music)"  
- **mel_features/**: the Mel spectrogram feature extracted from the audio of each sample
- **mfcc/**: the MFCCs feature extracted from the audio of each sample
- **vgg_features/**: the [VGGish](https://arxiv.org/pdf/1609.09430.pdf) feature extracted from the audio of each sample
- **TVSM-xxxx_metadata.csv**: the metadata of each sample 

For more information, please visit our paper

## Codebase introduction
```
└─── Evaluation_Output/
│    └─── AVASpeech/
│    │    └─── T2
│    │    └─── TVSM-cuesheet
│    │    └─── TVSM-pseudo
│    └─── ...
└─── Models/
└─── training_code/
```

- **Evaluation_Output**: the output generated by three models across five evaluation sets
  - T2: baseline method  
  - TVSM-cuesheet: CRNN-P-Cue method  
  - TVSM-pseudo: CRNN-P-Pseu method  
- **Models**: the pre-trained checkpoint from CRNN-P-Cue and CRNN-P-Pseu methods
- **training_code**: code for training the model

## Contact
Please feel free to contact [yhung33@gatech.edu](mailto:yhung33@gatech.edu) or open an issue here if you have any questions about the dataset or the support code.
