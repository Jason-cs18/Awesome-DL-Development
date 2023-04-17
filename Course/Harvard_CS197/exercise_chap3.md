# Exercises for chapter 3
1. Perform a similar summarization of the abstract for another method using the benchmarks. Look for active image captioning benchmarks where you see recent submissions, especially if the recent submissions are setting new SOTA.
    - OFA: Unifying Architectures, Tasks, and Modalities Through a Simple Sequence-to-Sequence Learning Framework
      - What is OFA? OFA is a task-agnostic and modality-agnostic framework to enable a unified multimodal pre-training paradigm. 
      - Previous efforts: state-of-the-art vision & language models depend on extremely large cross-modal datasets.
      - Their efforts: OFA conducts a simple sequence-to-sequence learning framework on 20M publicly available image-text pairs. Moreover, OFA supports instruction-based learning and does not require task-specific layers for downstream tasks.
      - Experimental results: SOTA results and easy-to-transfer across tasks and domains.
2. Repeat this process, this time for the GIT paper.
   - GIT: A Generative Image-to-text Transformer for Vision and Language (2022)
     - What is GIT? GIT is a generative image-to-text transformer for vision-language tasks, such as image/video capation, question answer.
       - Q1: transformer architectures have not been tested on vision-language tasks? CLIP have been proposed in 2020. 
     - Previous efforts? most rely on complex structures (uni/multi-modal encoder/decoder), or depend on external modules such as object detectors/taggers and optical character recognition (OCR).
     - They efforts? a simple architecture containing one image encoder and one text decoder
     - Results: SOTA results on 12 challenging benchmarks, decent performance on generation-based image classification and scene text recognition. 
     - Related works:
       - VL pre-training:
       - External modules:
       - Scaling on VL tasks: