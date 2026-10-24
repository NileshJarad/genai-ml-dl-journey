# Mobile AI Interview Questions

## Model Selection & Conversion

1. How do you convert a PyTorch model to TFLite? What post-training quantization options exist?

2. What are the steps to convert a TensorFlow Keras model to Core ML format on iOS?

3. When choosing between TFLite and Core ML, what factors should you consider?

4. Explain int8 quantization. What is the accuracy impact compared to float32?

5. How do you compare model sizes across different frameworks (TF, Core ML, ONNX)?

## On-Device Inference

6. How do you optimize for CPU-only inference when deploying an ML model on mobile?

7. What is the difference between dynamic range quantization and full integer quantization?

8. How do GPU delegates work in TensorFlow Lite? What platforms support them?

9. How does Metal Performance Shaders (MPS) work on Apple Silicon devices?

10. What are NNAPI and its purpose for Android ML inference?

## Mobile Framework Choice

11. When building an AI-powered app, how do you choose between React Native, Flutter, Swift, and Kotlin?

12. What are the trade-offs of sharing ML code across iOS and Android (RN vs native)?

13. How does React Native's Fabric renderer work for rendering ML predictions?

14. What is the `ml` package in Flutter and how does it integrate ML models?

15. How do UIKit and SwiftUI differ when integrating Core ML models?

## Privacy & Offline Capability

16. How do local models (llama.cpp, ONNX Runtime Mobile) compare to cloud API models?

17. What are GGUF and Q formats? Why are they important for on-device inference?

18. How do you handle model updates on-device without violating user privacy?

19. How do you implement graceful degradation (offline mode) when connecting fails?

20. What are the privacy implications of using a user's camera with on-device ML?

## MediaPipe & Vision

21. How do MediaPipe's calculators work in a pipeline graph? Can you add custom calculators?

22. What is the difference between camera input streams and video frames in MediaPipe?

23. How do you optimize pose estimation for real-time 60fps on mobile devices?

24. What happens when MediaPipe falls back to slower processors? How do you handle it?

25. How do you use MediaPipe's object detection for barcode scanning on mobile?

## Application Integration

26. How would you integrate GPT-4o vision capabilities in a Flutter application?

27. How do you handle API authentication securely on mobile apps?

28. How do streaming responses from OpenAI work with mobile apps?

29. What are the considerations when running local LLMs (like Ollama) on mobile?

30. How do you implement retry logic for failed API calls in mobile apps?

## Performance & UX

31. How do you measure ML inference latency on a device? What tools would you use?

32. How do you handle thermal throttling on mobile devices during ML inference?

33. How do background ML processing work on iOS (BackgroundTasks vs. work loops)?

34. How do you manage battery consumption from ML inference on mobile?

35. How do you design a smooth user experience when showing ML model progress?

## Edge Cases & Cross-Platform

36. How do you handle different screen sizes and camera resolutions for ML features?

37. What are the iOS version compatibility issues when loading Core ML models?

38. How do you test ML functionality across different device types (high-end vs low-end)?

39. How do you maintain ML model versioning across app updates?

40. How do you handle iOS permission requests for camera, microphone, and photos when using ML?

## Competitive Analysis

41. Compare Google ML Kit vs. Apple Vision framework for face detection use cases.

42. How does TensorFlow Lite Support Library differ from TensorFlow Lite Runtime?

43. Compare ONNX Runtime Mobile vs. TFLite for cross-platform mobile deployment.

44. How do you benchmark Core ML vs. TensorFlow Lite on identical models?