# Generative AI Interview Questions

## Core Concepts

1. **Transformers**: Explain the self-attention mechanism in transformers. How does positional encoding work?

2. **Attention**: What is scaled dot-product attention? Why is it important? How do you compute attention scores?

3. **Tokenization**: How do BPE and WordPiece tokenization work? Why do we need subword tokenization?

4. **Pre-training**: What is pre-training? Describe next-token prediction, masked language modeling, and contrastive learning as pre-training objectives.

5. **Fine-tuning**: How does fine-tuning differ from pre-training? Explain full, parameter-efficient, and instruction-based fine-tuning.

6. **Prompt Engineering**: What is prompt engineering? Describe few-shot, zero-shot, chain-of-thought, and instruction tuning approaches.

7. **Scaling Laws**: What are scaling laws for language models? How do compute, data, and model size affect performance?

8. **Evaluation**: How do you evaluate LLMs? List automatic metrics (BLEU, ROUGE, BERTScore), benchmarks, and human evaluation methods.

## Practical Questions

9. Design a RAG system that answers questions from technical documentation. Which components would you need and what's your architecture?

10. How would you fine-tune an LLM on custom code completion data? Describe the dataset preparation, choice of fine-tuning method, and evaluation.

11. Build a simple Agent framework that supports tool calling using OpenAI function calling. Describe your design.

12. How would you ensure an LLM generates factual, accurate responses? Discuss alignment techniques (RLHF, DPO, Constitutional AI).

13. What are the ethical considerations when using generative AI in production? Discuss bias, hallucination, privacy, and safety.

14. How do you handle long context windows in LLMs? Compare sliding window, compression, and chunked processing approaches.

15. Implement temperature sampling for text generation. Show the mathematical formulation and coding approach.

## Advanced Topics

16. Explain the difference between base models and instruction-tuned models. What is the role of RLHF?

17. How do contrastive learning and masked language modeling contribute to LLM training?

18. What are agentic AI systems? Compare LangChain agents, AutoGen agents, and LlamaIndex agents.

19. How do you design a system that retrieves relevant documents before generating an answer?

20. What is the difference between prompt tuning, prefix tuning, and prompt-based fine-tuning?

21. Compare open-source and closed-source LLM APIs. What are the trade-offs?

22. How do you test whether a generative AI model is actually generating useful output rather than random noise?