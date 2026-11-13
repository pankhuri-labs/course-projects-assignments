# Gesture Recognition for Smart TVs (3D CNN and CNN + RNN)

**Course:** Executive PG Programme in ML & AI, IIIT Bangalore · **Type:** Case study · **Year:** 2022

## Problem
A smart-TV maker wants users to control the TV with five hand gestures (thumbs up, thumbs down, swipe left, swipe right, stop) captured by a webcam. Each gesture is a short video of 30 frames.

## Approach
- Wrote a custom Python generator that reads, crops, resizes and normalises frame sequences in batches.
- Ran experiments on frame count, image size and batch size to balance accuracy against training time. Frame count drove training time far more than batch size.
- Trained and compared several architectures: Conv3D networks and CNN + RNN (time-distributed CNN feeding GRU/LSTM layers), with dropout, batch normalisation, learning-rate reduction and checkpointing.

## Results
- Final model: **99.5% training accuracy and 87.5% validation accuracy**.
- Experiment log in the notebook shows how each change affected overfitting and model size.

## Tools
Python, TensorFlow/Keras (Conv3D, TimeDistributed, GRU/LSTM), scikit-image, imageio, NumPy

## Files
- [`gesture_recognition.ipynb`](gesture_recognition.ipynb)

Originally published at [pankhurimishra81/GestureRecognition_RNN](https://github.com/pankhurimishra81/GestureRecognition_RNN).
