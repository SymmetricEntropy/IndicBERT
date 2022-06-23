# IndicBERT

<div align="center">
	<h1><b><i>IndicBERT</i></b></h1>
	<a href="">Website</a> |
	<a href="">Paper</a>
</div>

**IndicBERT** is a Multilingual RoBERTa BASE model trained on [Kosha](), which is the largest publicly available monolingual corpora collection for Indian lanagues at the time of writing (June 2022). IndicBERT is the best performing?? model on the Parikshinam Benchmark for Indian languages. We currently release the BASE model and will soon release the LARGE checkpoint. We support the following set of languages.

| <!-- -->      | <!-- -->       | <!-- -->       | <!-- -->       |                |             |
| ------------- | -------------- | -------------- | -------------- |--------------- |------------ |
| Assamese (as) | English (en)   | Khasi (kha)    | Malayalam (ml) | Odia (or)      | Sindhi (sd) |
| Bodo (db)     | Konkani (gom)  | Kannada (kn)   | Manipuri (mni) | Punjabi (pa)   | Tamil (ta)  |
| Bengali (bn)  | Gujarati (gu)  | Kashmiri (ks)  | Marathi (mr)   | Sanskrit (sa)  | Telugu (te) |
| Dogri (dg)    | Hindi (hi)     | Maithili (mai) | Nepali (ne)    | Santhali (sat) | Urdu (ur)   |

### Benchamrks

We evaluate IndicBERT on Parikshinam Benckmark. It outperforms
all publicly available open source models ??. The results are available below

#### Table of Results

## Updates
<details><summary> Click to expand </summary>
June 2022

```
Open-sourced Monolingual corpora and model checkpoints
```
</details>

## Table of contents
- [Resources](#resources)
  - [Try out model online (Huggingface spaces)](#try-out-model-online-huggingface-spaces)
  - [Download model](#download-model)
  - [Using hosted APIs](#using-hosted-apis)
    - [Sample screenshot of translate_sentence POST request](#sample-screenshot-of-translate_sentence-post-request)
  - [Accessing on ULCA](#accessing-on-ulca)
- [Running Inference](#running-inference)
  - [Command line interface](#command-line-interface)
  - [Python Inference](#python-inference)
- [Training model](#training-model)
  - [Setting up your environment](#setting-up-your-environment)
  - [Details of models and hyperparameters](#details-of-models-and-hyperparameters)
  - [Training procedure and code](#training-procedure-and-code)
  - [WandB plots](#wandb-plots)
  - [Evaluating trained model](#evaluating-trained-model)
  - [Detailed benchmarking results](#detailed-benchmarking-results)
- [Finetuning model on your data](#finetuning-model-on-your-data)
- [License](#license)
- [Contributors](#contributors)
- [Contact](#contact)


<short description of model and results>
    <include links to website, paper, video (if there is a recorded talk), Hosted inference link>
	<Rolling updates section to indicate major changes made to the repo and data/model releases>
    <table of contents>

## Resources

### Dataset

- Download the Kosha Corpora from [here]()

### Try out model on Huggingface spaces

- Model will be available soon

### Download model

- IndicBERT BASE: [click to download]()
- IndicBERT LARGE: [click to download]()
- IndicBERT models: [Mirror links]()

## Training Model

###  Setting up your environment
<details><summary>Click to expand </summary>

Requirements
```
CUDA=11.3.2
transformers=4.11.3
datasets=2.3.1
pytorch=1.11.0
accelerate=0.9.0
```

```bash
venv -m <ENV_NAME>
source <ENV_NAME>/bin/activate
pip3 install transformers==4.11.3 datasets==2.3.1 wandb sentencepiece==0.1.96 accelerate==0.9.0

pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu113
```
</details>

### Details of models and hyperparameters

- Architechture:
    - BASE: XLM-RoBERTa: encoder layers 12, hidden size 768, attention heads 12, activation gelu
    - LARGE: coming soon
- Loss: Cross Entropy Loss
- Optimizer: AdamW
- Learning rate: 5e-4
- Warmup_steps: 50000
- Max Seq Length: 512
- Global Batch Size: 4096

## Trying the model:

<some code example which uses our python modules>

```python
<import libs>
<import inference modules>

model = <initialize model>

# code for single file inference
...

# code for batch inference
...

# code to integrate with langauge model
...


```

<Colab notebook to try out these above steps - setup env, download sample audio, download model and do all the above inference>


## Replicate paper results

<provide bash scripts which can download benchmarks, checkpoints and produce the paper's results>
<colab notebook to show how to run:
         above bash script(with env creation, etc),
         Training instructions (how we did training for the paper):
           Download training data and preprocessing
           Provide training script with hyperparameter and some insights (Eg high bath sizes with low learning rate works well, fp16 is unstable etc)
           >
<add wandb plot link to help people check if they are on the right track>

## Finetuning the model on your own data
<Point out bash scripts that can help with this>
<colab notebook to show how to run above script. This includes:
        Data preparation for custom data (provide some useful links for format conv, eg mps, 3gp to wav format)
        Finetnuing script with hyperparameter details and some insights (eg low learning rate, less no of epochs to prevent overfitting etc)>

<add wandb plot link to help people check if they are on the right track>

## Folder Structure for git repo

<provide tree structure of the files used in the repo which will help advanced users to understand the codebase better and also help with pull requests from other users who want feature addition>
```
```

## Things to add / Future work (?)

## Citing

If you are using any of the resources, please cite the following article:
```
```

We would like to hear from you if:

- You are using our resources. Please let us know how you are putting these resources to use.
- You have any feedback on these resources.



### License
The IndicBERT code (and models) are released under the MIT License.


### Contributors

- Sumanth Doddapaneni, <sub>([AI4Bharat](https://ai4bharat.org), [IITM](https://www.iitm.ac.in))</sub>
- Gowtham Ramesh, <sub>([AI4Bharat](https://ai4bharat.org), [IITM](https://www.iitm.ac.in))</sub>
- Rahul Aralikatte
- Shreya Goyal
- Anoop Kunchukuttan, <sub>([Microsoft](https://www.microsoft.com/en-in/), [AI4Bharat](https://ai4bharat.org))</sub>
- Pratyush Kumar, <sub>([Microsoft](https://www.microsoft.com/en-in/), [AI4Bharat](https://ai4bharat.org), [IITM](https://www.iitm.ac.in))</sub>
- Mitesh M. Khapra, <sub>([AI4Bharat](https://ai4bharat.org), [IITM](https://www.iitm.ac.in))</sub>


### Contact

- Sumanth Doddapaneni ([sumanth.doddapaneni@gmail.com](mailto:sumanth.doddapaneni@gmail.com))
- Anoop Kunchukuttan ([anoop.kunchukuttan@gmail.com](mailto:anoop.kunchukuttan@gmail.com))
- Mitesh Khapra ([miteshk@cse.iitm.ac.in](mailto:miteshk@cse.iitm.ac.in))
- Pratyush Kumar ([pratyush@cse.iitm.ac.in](mailto:pratyush@cse.iitm.ac.in))