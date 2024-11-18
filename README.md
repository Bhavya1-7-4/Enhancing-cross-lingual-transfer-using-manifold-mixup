# X-Mixup

Implementation of ICLR 2022 paper "[Enhancing Cross-lingual Transfer by Manifold Mixup](https://openreview.net/pdf?id=OjPmfr9GkVv)".

This project was made by taking above research paper as reference under the faculty guidance of Dept of CSE, NIT AndhraPradesh as a part of Summer Research Internship.


## Structure
```text
.
├── data                              # XTREME data and translation data
│   ├── xnli
│      ├── XNLI-MT-1.0
│      ├── XNLI-1.0          
│      ├── translate-test
│      ├── translate-dev
│      ├── translate-train-en  # back-translation data  
├── scripts
├── xmixup
├── README.md
└── requirements.txt
```

## Environment
```bash
pip install -r requirements.txt
```

## Data
Prepare data before the training phrase: 
* Step 1: Download XTREME data from [XTREME repo](https://github.com/google-research/xtreme) (Note that we should keep the label of test set for evaluation).
* Step 2: Download other translation data from [here](https://drive.google.com/drive/folders/1UysSbPfkMBzQb6m2x7aO2WyWQehW38F3?usp=sharing).
* Step 3: Organize data following the Structure part.

## Training & Evaluation
```bash
bash ./scripts/train.sh [pretrained_model] [task_name] [data_dir] [output_dir]
```
where the options are described as follows:
- `[pretrained_model]`: `xlmr` or `mbert`
- `[task_name]`: `xnli`
- `[data_dir]`: data directory
- `[output_dir]`: output directory
