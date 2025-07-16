# Multilingual Question-Answering Web App

A Flask-based web application that supports multilingual question answering. The answers are derived from textual data stored at `llm-script.txt`

## Features

- GPU acceleration with CUDA

## Setup Instructions

### 1. Prerequisites

- [CUDA Toolkit](https://developer.nvidia.com/cuda-12-8-0-download-archive) and a compatible GPU (or modify code to use CPU)
- [Hugging Face token](https://huggingface.co/settings/tokens) for API access

### 2. Setup

- Set Hugging Face Token as an environment variable:

```
set HF_TOKEN=your_token_here
```
- Install required libraries
```
pip install --no-cache-dir -r requirements.txt
```

- Install PyTorch wheels based on your CUDA version (examples):

##### For CUDA 12.6
```
pip install --no-cache-dir torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu126
```

##### For CUDA 12.8
```
pip install --no-cache-dir torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128
```

## Run
```
python flask_app.py
```

## Additional
- DeepSeek can be used to rephrase the answers into declarative statements but the model produces inconsistent results due to lack of proper deepseek_prompt[]. Using DeepSeek also increases computational time. The code is still included in code but disabled by default. Enable if needed by commenting/uncommenting relevant lines

- The textual data stored at `llm-script.txt` is currently unformatted and therefore less accurate. It can be formatted into declarative statements and each statement can be put on a new line for better results

- Tested on Windows 10 64-bit with RTX-4070 and 12 GB GPU memory. ( It is not the minimum requirement and should work on comparatively weaker computers)