# HuggingFace
- Learning path:
  - make sure your needs in advance (what can we learn from docs?)
  - go through the docs and organize them to meet your demand (how to solve them?)
- xxx minutes tutorial:
  - [Sign up HuggingFace](https://huggingface.co/join) to join the community.
  - [Search the task](https://huggingface.co/tasks) to understand recent advances (models, metrics and papers).
  - [Go through the doc](https://huggingface.co/docs/transformers/index) to know xxx.
  - Deploy your model(s) via [HuggingFace Inference API](https://huggingface.co/inference-api). *It seems like a black-box inference engine for developers. Thus, I still recommend using open-source inference servers like NVIDIA Triton for better customization and extension.*
- Components
  - [Models](https://huggingface.co/models): A model zoo for diverse tasks of different domains (multimodal, computer vision, natural language processing, audio, tabular, and reinforcement learning).
  - [Datasets](https://huggingface.co/datasets): A dataset collection for diverse tasks of different domains (multimodal, computer vision, natural language processing, audio and tabular).
  - [Spaces](https://huggingface.co/spaces): Recent trends on ML apps.
  - [Docs](https://huggingface.co/docs): Official documentation (*I highly recommend you go through it in advance*)
    - Transformers
    - Diffusers
    - Hub
    - Datasets
    - Gradio
    - Hub Python Library
    - Huggingface.js
    - Inference API
    - Inference Endpoints
    - Accelerate
    - Optimum
    - Tokenizers
    - Evaluate
    - Tasks
    - Datasets-server
    - Simulate
    - Amazon SageMaker
    - timm
    - Safetensors
    - AutoTrain
## DL/ML engineering
- ML development
  - Use pre-trained models for inference (Model-as-a-Service)
  - Create a new model architecture
  - Train the model with supported/customized datasets
  - Accelerate the training job via distributed training
  - Profile the model on accuracy and efficiency
  - Test the model on supported/customized datasets
- ML deployment
  - Optimize the trained model for inference
  - Deploy the optimized model and monitor its performance
## Use pre-trained models for inference
1. NLP (text classification, zero-shot classification, text generation, text completion, token classification, question answering, summarization, translation).
    ```python
    # text generation
    from transformers import pipeline
    generator = pipeline("text-generation")  # using the default model
    generator = pipeline("text-generation", model="distilgpt2")  # using the specific model
    generator("In this course, we will guide you how to")  # preprocessing, inference, post-processing
    ```
2. CV (depth estimation, image classification, image segmentation, image-to-image, object detection, video classification, unconditional image generation, zero-shot image classification).
    ```python
    # zero-shot image classification
    # object detection
    # image segmentation
    ```