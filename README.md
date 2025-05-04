# Enhancing Synthetic Speech Naturalness Through Optimal Transport

This repository contains the code and other resources for the project "Enhancing Synthetic Speech Naturalness Through Optimal Transport", developed as part of my cpastone project at RIT. The goal of this project is to improve the naturalness of synthetic speech by aligning its acoustic representations with those of real human speech using Optimal Transport (OT).

# Motivation:

Synthetic speech often sounds unnatural due to issues in prosody, pronunciation, and rhythm. This project investigates how Optimal Transport—a mathematical technique used to align probability distributions—can improve the quality of generated speech. The improvements are evaluated through human feedback and automatic spoof detection scores using the AASIST model.

# System Pipeline:

 <h1 align = "center"><img src="https://github.com/mu9326/OT-Speech-Enhancement/blob/main/sys_pipeline.png" width="300" /></h1>

* *Data Preparation: Load bonafide and spoofed speech samples from the ASVspoof2019 dataset.*
* *Embedding Generation: Extract speech embeddings using the pretrained WavLM model.*
* *OT-Based Alignment: Apply the Sinkhorn algorithm to align spoofed embeddings to the distribution of natural speech.*
* *Reconstruction: Convert mapped embeddings to mel-spectrograms and reconstruct audio using HiFi-GAN vocoder.*
* *Evaluation:*
*   *Subjective: Human listening tests for prosody and phonetic quality.*
*   *Objective: AASIST model's probability of detecting speech as fake.*

# Results:

AASIST score (fake → real probability):
    * Original fake: 0.97*
    * After vocoding: 0.72*
    * After OT + vocoding: 0.43

This reduction indicates that OT-based alignment significantly improves the realism of generated speech.

 <h1 align = "center"><img src="https://github.com/mu9326/OT-Speech-Enhancement/blob/main/results.png" width="300" /></h1>

# Citation:
@misc{udasi2025otspeech,
  title={Enhancing Synthetic Speech Naturalness Through Optimal Transport},
  author={Dr. Anton Selitskiy, Mona Anil Udasi},
  year={2025},
  note={Capstone Project Poster, RIT}
}


