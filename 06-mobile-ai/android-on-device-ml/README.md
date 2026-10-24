# Android On-Device ML

## Overview

TensorFlow Lite (TFLite) enables efficient machine learning on Android devices. It provides:

- Hardware acceleration (GPU, NNAPI, Hexagon)
- Model optimization (quantization, pruning)
- Fast inference with low latency
- Reduced model sizes

## Key Components

### Model Conversion
- `tflite_convert` for TensorFlow models
- Post-training quantization
- Quantization-aware training
- Model optimization for different hardware

### Android Integration
- TensorFlow Lite Interpreter
- TensorFlow Lite Support Library
- TensorFlow Lite Task Library
- GPU delegate setup

## Optimization Techniques

1. **Quantization**
   - Float16 quantization
   - Int8 quantization
   - Dynamic range quantization
   - Full integer quantization

2. **Model Pruning**
   - Weight pruning
   - Structured pruning
   - Unstructured pruning

3. **Hardware Acceleration**
   - GPU delegate
   - NNAPI delegate
   - Hexagon DSP delegate

## Common Use Cases

- Image classification
- Pose estimation
- Text recognition
- Speech recognition
- Anomaly detection in sensor data

## Tools and Libraries

- TensorFlow Lite
- ML Kit (Google)
- ONNX Runtime Mobile
- Arm NN

## Best Practices

- Profile inference latency
- Monitor memory usage
- Handle device compatibility
- Implement fallback strategies
- Test on various hardware