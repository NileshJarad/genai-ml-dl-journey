# 05 Image Captioning Mobile App

## Overview
Mobile application that generates descriptive captions for images using vision models.

## Architecture
1. **Image Input**
   - Camera capture
   - Photo library selection
   - Image preprocessing

2. **Feature Extraction**
   - Vision model (CNN/ViT)
   - Feature embeddings
   - Region of interest detection (optional)

3. **Caption Generation**
   - Auto-regressive generation (decoder-only transformer)
   - Beam search / sampling
   - Post-processing (grammar correction)

4. **Output**
   - Generated caption text
   - Confidence scores
   - Alternative captions
   - Save/share options

## Features
- [x] Camera integration
- [x] Photo library access
- [x] Multiple caption styles (descriptive, concise, creative)
- [x] Multi-language support
- [x] Save to gallery
- [ ] Real-time video captioning
- [ ] Custom domain adaptation
- [ ] Multi-image comparison
- [ ] Style transfer in captions

## Model Options
| Model | Size | Quality | Speed |
|-------|------|---------|-------|
| BLIP-2 (Vicuna) | 1B-2B | High | Medium |
| Flamingo | 3.5B | High | Slow |
| mplug | 1B | Medium | Fast |
| MiniGPT-4 | 2.7B | Medium | Medium |
| LLaVA | 7B | High | Slow |
| Qwen-VL | 7B | High | Medium |
| InternVL | 8B | Very High | Slow |

## Tech Stack
- Vision model: LLaVA, BLIP-2, Qwen-VL
- LLM: Llama.cpp, Ollama
- Mobile: React Native / Swift / Kotlin
- Camera: ImagePicker, Camera library
- TFLite conversion for inference

## API Endpoints
- `POST /caption` - Generate caption for image
- `POST /captions/batch` - Batch process images
- `GET /styles` - Available caption styles

## Evaluation Metrics
- CIDEr score (caption quality)
- BLEU / ROUGE (text similarity)
- Human evaluation (quality rating)
- Inference latency
- Model size

## Best Practices
1. Use appropriate model size for target device
2. Implement TFLite quantization
3. Handle various image formats and sizes
4. Provide fallback captions on errors
5. Cache recent generations
6. User consent for image processing