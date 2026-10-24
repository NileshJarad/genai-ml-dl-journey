# 04 Voice Assistant

## Overview
A local voice assistant that can:
- Speech recognition (STT)
- Natural language understanding
- Task execution
- Text-to-speech (TTS)

## Architecture
1. **Audio Input**
   - Microphone capture
   - Noise reduction
   - Audio format conversion

2. **Speech-to-Text (STT)**
   - Whisper.cpp
   - OpenAI Whisper API
   - Edge-optimized models

3. **NLU & Intent Understanding**
   - Intent classification
   - Entity extraction
   - Context management

4. **Action Execution**
   - Local commands (calendar, notes, messages)
   - API integrations (weather, news, smart home)
   - LLM reasoning

5. **Text-to-Speech (TTS)**
   - Edge TTS / Coqui TTS
   - OpenAI TTS
   - Voice cloning/custom voices

6. **Response Generation**
   - LLM response
   - Response formatting
   - Voice selection and prosody

## Features
- [x] Offline STT capability
- [x] Multi-language support
- [x] Context-aware conversations
- [x] Command execution
- [x] Fallback to cloud API
- [ ] Wake word detection
- [ ] Multi-user support
- [ ] Custom voice personality
- [ ] Long-form conversation memory

## Tech Stack
- STT: Whisper.cpp, OpenAI Whisper
- LLM: Llama.cpp, Ollama, or cloud API
- TTS: Edge TTS, Coqui, OpenAI
- Framework: Ollama, LangChain, custom

## Use Cases
- Smart home control
- Information queries (weather, news, trivia)
- Calendar and scheduling
- Message dictation
- Reminders and alerts
- Math calculations
- Unit conversions

## API Endpoints
- `POST /speech-to-text` - Transcribe audio
- `POST /chat` - Process user intent
- `POST /text-to-speech` - Generate audio response
- `GET /health` - Service health check

## Evaluation Metrics
- STT accuracy (word error rate)
- Intent classification accuracy
- Response latency (end-to-end)
- TTS naturalness rating
- Fallback rate (cloud when offline)