# Comparative Opinion Mining in VLSP 2023 shared task
This repo contains code and dataset of our methods to solve VLSP2023 ComOM shared task.

## Task definition
Comparative Opinion Mining aims to identify comparative sentences and extract comparative opinion elements in the sentences (Subject, Object, Aspect, Predicate, Comparison Type
Label).

## Dataset
We use dataset in Vietnamese language which is provided by VLSP2023 ComOM shared task organizers

## Methods
We fine-tuned the multi-stage model used for bench-mark this task in English and Chinese from Ziheng Liu, Rui Xia, and Jianfei Yu. Comparative Opinion Quintuple Extraction from Product Reviews. EMNLP 2021.

## Installation and Run
We divide our code into two branches : main and codeoutput. In particular, we train our model in branch main and generate output format in branch codeoutput.

### Training data
Clone the repository of our project in branch 'main'

```
!git clone https://github.com/duyvu1110/ComOM_VLSP2023.git
```
Install packages 

```
!pip install -q transformers pytorch-crf
```
Make the following directories 

```
!mkdir 'path/ComOM_VLSP2023/data/pre_process'
!mkdir 'path/ComOM_VLSP2023/multi_stage_approach/ModelResult'
!mkdir 'path/ComOM_VLSP2023/multi_stage_approach/PreTrainModel'
```
Start train data 

```
!bash run.sh
```

### Generate output
After finish training data, there are three models saved in folder PreTrainModel including dev_model, dev_pair_model, dev_polarity_model. To generate output following these steps:

#### Step 1: Clone branch codeoutput
```
git clone -b codeoutput https://github.com/duyvu1110/ComOM_VLSP2023.git
```

#### Step 2: Move the output folder PreTrainModel from training phase to the newly cloned folder

#### Step 3: Put test data in the data folder
Example: 'path/ComOM_VLSP2023//data/smartphone/VLSP2023_ComOM_testing_v2/test_0001.txt'

#### Step 4: Make sure packages all installed and directories are prepared like training phase

#### Step 5: Start generate output

```
!bash run.sh
```


## References
Liu, Z., Xia, R., and Yu, J. (2021). Comparative
opinion quintuple extraction from product re-
views. In Proceedings of the 2021 Conference
on Empirical Methods in Natural Language Pro-
cessing, pages 3955–3965.

Le, H.-Q., Can, D.-C., Nguyen, K.-V., and Tran,
M.-V. (2023). Overview of the vlsp 2023 - co-
mom shared task: A data challenge for compar-
ative opinion mining from vietnamese product
reviews. In Proceedings of the 10th International
Workshop on Vietnamese Language and Speech
Processing.








