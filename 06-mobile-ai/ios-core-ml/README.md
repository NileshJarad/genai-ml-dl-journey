# iOS Core ML

## Overview

Core ML is Apple's framework for integrating machine learning models into iOS, macOS, watchOS, and tvOS applications. It provides:

- Hardware acceleration (Neural Engine, GPU, CPU)
- On-device processing with privacy
- Seamless integration with Swift and Objective-C
- Model conversion from popular frameworks

## Key Components

### Core ML Framework
- `MLModel` for model loading and prediction
- `MLFeatureProvider` for input/output handling
- `MLModelConfiguration` for performance tuning

### Core ML Tools (coremltools)
- Model conversion from PyTorch, TensorFlow, ONNX
- Model optimization (quantization, pruning)
- Model metadata and specification
- Deployment utilities

### Create ML
- No-code model training
- Transfer learning for images, text, tabular data
- Model evaluation and testing
- Export to Core ML format

## Model Conversion

### Supported Formats
- TensorFlow/Keras (.h5, .pb, SavedModel)
- PyTorch (.pt, .pth via ONNX)
- ONNX (.onnx)
- Scikit-learn, XGBoost, LightGBM

### Conversion Process
```python
import coremltools as ct

# From PyTorch via ONNX
model = ct.convert(onnx_model, ...)

# From TensorFlow
model = ct.convert(tf_model, ...)
```

## Optimization

### Quantization
- 16-bit float quantization
- 8-bit integer quantization
- Layer-wise quantization
- Mixed precision quantization

### Pruning
- Weight pruning with magnitude threshold
- Structured pruning
- Unstructured pruning

## iOS Integration

### Swift Integration
```swift
let model = try MyModel(configuration: MLModelConfiguration())
let prediction = try model.prediction(input: MyModelInput(...))
```

### Performance Tuning
- `MLModelConfiguration.computeUnits` (CPU, GPU, Neural Engine)
- Batch inference
- Asynchronous execution
- Model compilation and caching

## Best Practices

- Profile on actual devices
- Use appropriate compute units
- Handle model versioning
- Test across iOS versions
- Optimize for app size

## Common Use Cases

- Image classification and detection
- Style transfer and image generation
- Text classification and NLP
- Sound classification
- Activity recognition
- Tabular data prediction