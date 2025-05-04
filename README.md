# Enhancing Synthetic Speech Naturalness Through Optimal Transport

This repository contains the code and other resources for the project "Enhancing Synthetic Speech Naturalness Through Optimal Transport", developed as part of my cpastone project at RIT. The goal of this project is to improve the naturalness of synthetic speech by aligning its acoustic representations with those of real human speech using Optimal Transport (OT).

# Motivation:

Synthetic speech often sounds unnatural due to issues in prosody, pronunciation, and rhythm. This project investigates how Optimal Transport—a mathematical technique used to align probability distributions—can improve the quality of generated speech. The improvements are evaluated through human feedback and automatic spoof detection scores using the AASIST model.

# System Pipeline:
- Data Preparation: Load bonafide and spoofed speech samples from the ASVspoof2019 dataset.
- Embedding Generation: Extract speech embeddings using the pretrained WavLM model.
- OT-Based Alignment: Apply the Sinkhorn algorithm to align spoofed embeddings to the distribution of natural speech.
- Reconstruction: Convert mapped embeddings to mel-spectrograms and reconstruct audio using HiFi-GAN vocoder.
- Evaluation:
    - Subjective: Human listening tests for prosody and phonetic quality.
    - Objective: AASIST model's probability of detecting speech as fake.

 <h1 align = "center"><img src="https://github.com/mu9326/OT-Speech-Enhancement/blob/main/sys_pipeline.png" width="300" /></h1>

# Results:
Human evaluations on selected speech samples showed slight improvements in prosody and phonetic quality after applying OT. In contrast, AASIST, which outputs a probability score for how likely speech is fake, revealed the following results:
- Fake speech was initially detected with an extremely high score of 0.97.
- Applying OT significantly reduced the detection score to 0.43.
- Vocoding alone slightly reduced the score to 0.72 but was not sufficient.
- This confirms that OT-driven alignment, not just vocoding, contributed meaningfully to reducing detectability.

 <h1 align = "center"><img src="https://github.com/mu9326/OT-Speech-Enhancement/blob/main/results.png" width="300" /></h1>

Key Insight:
While vocoding alone improves surface quality, Optimal Transport meaningfully aligns deep acoustic embeddings, reducing the chances of synthetic speech being detected as fake by a robust deepfake detector like AASIST.


# Citation:
@misc{udasi2025otspeech,
  title={Enhancing Synthetic Speech Naturalness Through Optimal Transport},
  author={Dr. Anton Selitskiy, Mona Anil Udasi},
  year={2025},
  note={Capstone Project Poster, RIT}
}


