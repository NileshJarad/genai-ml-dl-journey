# Local LLMs on Mobile

## Overview

Running LLMs locally on mobile devices provides:

- Privacy (no data leaves device)
- Offline capability
- No API costs
- Low latency (no network round-trip)
- Control over model behavior

## Challenges

- Model size (typically 1-7B parameters)
- Memory constraints (RAM, storage)
- Compute limitations (CPU, GPU, NPU)
- Battery life
- Thermal throttling

## Solutions and Frameworks

### Mobile-Optimized Models

| Model | Parameters | Quantized Size | Platform |
|-------|-----------|----------------|----------|
| Llama 3.2 1B/3B | 1B/3B | ~600MB/2GB | iOS/Android |
| Phi-3 Mini | 3.8B | ~2.2GB | iOS/Android |
| Gemma 2 2B | 2B | ~1.2GB | iOS/Android |
| Qwen 2.5 1.5B/3B | 1.5B/3B | ~900MB/2GB | iOS/Android |
| SmolLM 1.7B | 1.7B | ~1GB | iOS/Android |

### Inference Engines

#### llama.cpp / GGUF
- CPU-optimized inference
- GGUF format (quantized)
- Cross-platform (iOS, Android, Linux)
- Metal/GPU support on Apple Silicon

```bash
# Convert to GGUF
python convert.py --model-path llama-3.2-3b --outtype q4_k_m
```

#### MLC LLM
- GPU-accelerated via Metal/Vulkan
- Apache TVM compilation
- Pre-built model libraries
- Python, Swift, Kotlin bindings

#### ExecuTorch (PyTorch)
- PyTorch-native mobile deployment
- Export to .pte format
- Core ML / NNAPI / XNNPACK backends
- Dynamic shapes support

#### ONNX Runtime Mobile
- ONNX model format
- Cross-platform
- Quantization support
- Mobile-optimized kernels

### Apple-Specific

#### MLX (Apple Silicon)
- Array framework for ML
- Metal-accelerated
- Python API
- Optimized for M-series chips

#### Core ML
- Convert with coremltools
- Neural Engine acceleration
- Swift integration

## Quantization

| Method | Bits | Quality | Speed | Size |
|--------|------|---------|-------|------|
| Q8_0 | 8 | High | Fast | Large |
| Q4_K_M | 4 | Good | Very Fast | Medium |
| Q4_K_S | 4 | Good | Fastest | Small |
| Q3_K_M | 3 | Decent | Fast | Small |
| Q2_K | 2 | Low | Fast | Smallest |

## Implementation Patterns

### Android (Kotlin)
```kotlin
// Using llama.cpp Android bindings
val model = LlamaModel.fromAssets(context, "model-q4_k.gguf")
val context = model.createContext()
val response = context.generate("Hello!")
```

### iOS (Swift)
```swift
// Using llama.cpp Swift bindings
let model = LlamaModel.fromFile("model-q4_k.gguf")
let context = try model.createContext()
let tokens = try context.generate("Hello!")
```

### Python (Development)
```python
from llama_cpp import Llama

llm = Llama(model_path="model-q4_k.gguf", n_gpu_layers=-1)
output = llm("Hello!", max_tokens=100)
```

## Use Cases

- Offline chat assistants
- Document summarization on-device
- Code completion without cloud
- Translation without internet
- Personal AI assistants
- Privacy-sensitive applications

## Best Practices

1. Choose right model size for device
2. Use appropriate quantization
3. Profile memory and battery
4. Implement streaming responses
5. Handle thermal state
6. Manage model updates
7. Test on diverse devices