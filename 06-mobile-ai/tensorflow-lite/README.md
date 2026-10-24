# TensorFlow Lite

## Overview

TensorFlow Lite is Google's open-source framework for deploying ML models on mobile, embedded, and IoT devices. It provides:

- Cross-platform support (Android, iOS, Linux, microcontrollers)
- Hardware acceleration
- Model optimization
- Small binary size

## Key Features

### Model Format
- FlatBuffer format (.tflite)
- Efficient serialization
- Version compatibility
- Metadata support

### Hardware Acceleration
- GPU delegate (OpenGL, Metal, Vulkan)
- NNAPI delegate (Android)
- Core ML delegate (iOS)
- Hexagon DSP delegate
- Edge TPU delegate (Coral)

### Optimization
- Post-training quantization
- Quantization-aware training
- Model pruning
- Operator fusion

## Conversion

### From TensorFlow
```python
import tensorflow as tf

converter = tf.lite.TFLiteConverter.from_saved_model(saved_model_dir)
tflite_model = converter.convert()
```

### From Keras
```python
converter = tf.lite.TFLiteConverter.from_keras_model(model)
```

### From ONNX (experimental)
```python
import onnx
import tf2onnx

onnx_model = onnx.load(model_path)
tflite_model = convert_onnx_to_tflite(onnx_model)
```

## Quantization Types

| Type | Size Reduction | Accuracy Impact | Speed |
|------|----------------|-----------------|-------|
| Float16 | ~2x | Minimal | Good |
| Dynamic Range | ~4x | Low | Better |
| Full Integer | ~4x | Moderate | Best |
| Weight Only | ~4x | Low | Good |

## Interpreter API

### Python
```python
import tensorflow as tf

interpreter = tf.lite.Interpreter(model_path="model.tflite")
interpreter.allocate_tensors()
input_details = interpreter.get_input_details()
output_details = interpreter.get_output_details()
```

### C++
```cpp
#include "tensorflow/lite/interpreter.h"
#include "tensorflow/lite/model.h"

std::unique_ptr<tflite::FlatBufferModel> model =
    tflite::FlatBufferModel::BuildFromFile("model.tflite");
tflite::ops::builtin::BuiltinOpResolver resolver;
tflite::InterpreterBuilder(*model, resolver)(&interpreter);
```

## Edge Cases

- **Model size constraints**: Use quantization, pruning
- **Latency requirements**: Profile, use GPU/NPU delegates
- **Memory limits**: Operator fusion, model splitting
- **Battery life**: Optimize for inference efficiency

## Tools

- `tflite_convert` - command line conversion
- `tflite_runtime` - lightweight runtime
- TensorFlow Model Optimization Toolkit
- Netron (model visualization)

## Best Practices

1. Always profile on target hardware
2. Test quantization accuracy
3. Handle input/output preprocessing
4. Implement graceful degradation
5. Monitor inference metrics