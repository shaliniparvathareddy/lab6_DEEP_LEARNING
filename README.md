Experiment 6 — RNN, LSTM, GRU and Video Understanding
Overview
This experiment studies recurrent neural networks for sequence learning and video understanding.

The experiment covers:

Vanilla RNN

LSTM

GRU

Backpropagation Through Time (BPTT)

Human Activity Recognition using sensor data

CNN feature extraction for video

CNN + LSTM/GRU video classification

Sequence-to-sequence learning

Dataset
The primary dataset used is the UCI Human Activity Recognition Using Smartphones (UCI HAR) dataset.

It contains six activity classes:

WALKING

WALKING_UPSTAIRS

WALKING_DOWNSTAIRS

SITTING

STANDING

LAYING

The raw sensor data is arranged as:

(samples, 128, 9)

where:

128 = sequence length

9 = sensor features per time step

A subset of approximately 1500–3000 samples can be used for the experiment.

Models
Three recurrent models are implemented using the same experimental settings:

Input (128 × 9)
      ↓
RNN / LSTM / GRU (32 units)
      ↓
Dropout (0.2)
      ↓
Dense (16, ReLU)
      ↓
Dense (6)
      ↓
Softmax

The models are compared using:

Accuracy

Macro Precision

Macro Recall

Macro F1-score

Confusion Matrix

Number of Parameters

Training Time

Video Understanding
The experiment also demonstrates video classification using a CNN and recurrent network.

The pipeline is:

Video
  ↓
Sample 10 Frames
  ↓
Resize to 224 × 224 × 3
  ↓
Pretrained MobileNetV2
  ↓
CNN Feature Vectors
  ↓
LSTM / GRU
  ↓
Classification

The CNN extracts spatial features from individual frames, while the recurrent network learns temporal information across the frames.

Sequence-to-Sequence Learning
A simple sequence reversal task is also implemented.

Example:

Input  : [1, 4, 7, 2]
Output : [2, 7, 4, 1]

This demonstrates the basic encoder-decoder architecture.

