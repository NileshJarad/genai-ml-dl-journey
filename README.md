# genai-ml-dl-journey

A comprehensive learning journey through Generative AI, Machine Learning, and Deep Learning.

## Overview

This repository documents a progressive learning path from foundational concepts to advanced applications in AI/ML/DL. It's organized as a structured journey with clear progression from basics to cutting-edge topics.

### Learning Path Structure

| Module | Code | Focus | Key Subtopics |
|--------|------|-------|---------------|
| **Roadmap** | `00-roadmap/` | Learning strategy | Roadmaps, weekly plans, progress tracking |
| **Python for AI** | `01-python-for-ai/` | Programming foundation | NumPy, Pandas, ML best practices |
| **Math for ML** | `02-math-for-ml/` | Mathematical foundations | Linear algebra, statistics, probability |
| **Machine Learning** | `03-machine-learning/` | Core algorithms | Data preprocessing, supervised/unsupervised, evaluation |
| **Deep Learning** | `04-deep-learning/` | Neural networks | CNNs, RNNs, Transformers, PyTorch/TensorFlow |
| **Generative AI** | `05-generative-ai/` | Modern AI | LLMs, prompt engineering, RAG, agents, fine-tuning |
| **Mobile AI** | `06-mobile-ai/` | On-device intelligence | Core ML, TFLite, MediaPipe, APIs |
| **Proof of Concepts** | `07-pocs/` | Real-world applications | 6 production-ready POC projects |
| **Interview Prep** | `08-interview-prep/` | Career readiness | Technical and system design interview questions |
| **Projects** | `09-projects/` | Portfolio building | Ideas, case studies, architecture diagrams |
| **Documentation** | `docs/` | Professional resources | Setup guides, standards, learning resources |

## Quick Start

### Installation

```bash
# Install project dependencies
pip install -r requirements.txt

# For development with linting and testing
pip install -e ".[dev]"

# Environment setup (copy and configure .env.example)
```

### Running

```bash
# Start Jupyter for interactive exploration
jupyter lab

# Run tests to verify setup
pytest

# Code quality checks
black .        # Format code
ruff check .  # Lint and fix imports
mypy .        # Type checking
```

## Directory Structure

```
genai-ml-dl-journey/
├── README.md                    # This overview
├── LICENSE                      # Project license
├── .gitignore                   # Version control exclusions
├── requirements.txt             # Python dependencies
├── pyproject.toml              # Build configuration
├── .env.example                 # Environment variables template
├── .claude/                    # Claude Code settings
├── .github/workflows/ci.yml    # CI/CD pipeline
├── 00-roadmap/                 # Learning roadmap and tracking
│   ├── learning-roadmap.md      # 24-week learning plan
│   ├── weekly-plan.md           # Weekly breakdowns
│   └── progress-tracker.md      # Progress monitoring
├── 01-python-for-ai/            # Python fundamentals
│   ├── concepts/                # Core concepts
│   ├── questions/              # Practice questions
│   └── notebooks/              # Interactive notebooks
├── 02-math-for-ml/              # Mathematics for ML
│   ├── concepts/                # Mathematical concepts
│   └── questions/              # Practice questions
├── 03-machine-learning/         # Traditional ML algorithms
│   ├── 01-data-preprocessing/   # Data cleaning and transformation
│   ├── 02-supervised-learning/ # Classification and regression
│   ├── 03-unsupervised-learning/# Clustering and dimensionality reduction
│   ├── 04-model-evaluation/    # Model assessment and validation
│   ├── 05-feature-engineering/ # Feature creation and selection
│   ├── concepts/              # ML concepts
│   ├── questions/            # Practice questions
│   └── notebooks/            # Interactive examples
├── 04-deep-learning/            # Neural network architectures
│   ├── 01-neural-networks/     # Fundamental neural networks
│   ├── 02-cnn/                # Convolutional neural networks
│   ├── 03-rnn/                # Recurrent neural networks
│   ├── 04-transformers/       # Transformer architecture
│   ├── 05-pytorch/            # PyTorch implementation
│   ├── 06-tensorflow/         # TensorFlow implementation
│   ├── concepts/              # Deep learning concepts
│   ├── questions/            # Practice questions
│   └── notebooks/            # Interactive examples
├── 05-generative-ai/            # Modern generative AI
│   ├── 01-llm-fundamentals/    # Large language models
│   ├── 02-prompt-engineering/  # Effective prompting
│   ├── 03-embeddings/          # Vector representations
│   ├── 04-vector-databases/   # Similarity search
│   ├── 05-rag/               # Retrieval-augmented generation
│   ├── 06-agents/            # AI agents
│   ├── 07-fine-tuning/        # Model fine-tuning
│   ├── 08-evaluation-and-safety/ # LLM safety and evaluation
│   ├── concepts/             # Generative AI concepts
│   ├── questions/           # Practice questions
│   └── notebooks/           # Interactive examples
├── 06-mobile-ai/               # Mobile device ML
│   ├── android-on-device-ml/  # Android TFLite deployment
│   ├── ios-core-ml/           # iOS Core ML integration
│   ├── tensorflow-lite/       # Cross-platform TFLite
│   ├── mediapipe/            # MediaPipe solutions
│   ├── gemini-api/           # Gemini API integration
│   ├── openai-api/           # OpenAI API for mobile
│   ├── local-llms/           # Local LLM deployment
│   └── pocs/                 # Mobile AI examples
├── 07-pocs/                    # Proof of concept projects
│   ├── 01-rag-document-assistant/    # Document Q&A system
│   ├── 02-ai-support-agent/          # Customer support bot
│   ├── 03-mobile-app-review-analyzer/ # App review analysis
│   ├── 04-voice-assistant/           # Voice interaction
│   ├── 05-image-captioning-mobile-app/# Image description generation
│   └── 06-tender-document-workflow/  # Document workflow automation
├── 08-interview-prep/           # Interview preparation
│   ├── ml-interview-questions.md            # ML technical questions
│   ├── dl-interview-questions.md            # Deep learning questions
│   ├── genai-interview-questions.md         # Generative AI questions
│   ├── system-design-ai.md                 # System design for AI
│   └── mobile-ai-interview-questions.md     # Mobile AI interviews
├── 09-projects/                # Portfolio projects
│   ├── project-ideas.md        # Project inspiration
│   ├── case-studies/          # Real-world project examples
│   └── architecture-diagrams/ # System architecture diagrams
├── docs/                       # Professional documentation
│   ├── setup-guide.md          # Installation and setup
│   ├── coding-standards.md     # Code quality standards
│   └── resources.md            # Learning resources
└── .github/                    # GitHub configuration
    └── workflows/ci.yml        # Continuous integration
```

## Key Features

### 1. **Progressive Learning Path**
- 9-week structured learning program
- Each module builds on previous knowledge
- Balance of theory and practical implementation

### 2. **Comprehensive Coverage**
- Traditional ML (scikit-learn, pandas)
- Deep Learning (PyTorch, TensorFlow)
- Generative AI (LLMs, transformers, RAG)
- Mobile deployment (TFLite, Core ML)

### 3. **Practical Applications**
- Real-world proof-of-concept projects
- Industry-relevant interview preparation
- Production-ready code examples

### 4. **Professional Tools**
- CI/CD pipeline for code quality
- Documentation standards and templates
- Environment configuration management

## Technologies and Tools

### Core Frameworks
- **Python**: NumPy, Pandas, Scikit-learn
- **Deep Learning**: PyTorch, TensorFlow, Keras
- **NLP**: Hugging Face Transformers
- **Mobile**: TensorFlow Lite, Core ML, MediaPipe

### Development Tools
- **Code Quality**: Black (formatting), Ruff (linting), MyPy (type checking)
- **Testing**: Pytest with notebook testing support
- **Documentation**: MkDocs for static site generation
- **Containerization**: Docker support

### Specialized Components
- **Vector Databases**: ChromaDB, Pinecone for RAG systems
- **LLM Integration**: OpenAI, Anthropic, Google APIs
- **Mobile APIs**: Google Gemini, OpenAI for mobile

## Learning Methodology

### 1. **Foundation First**
- Mathematical principles
- Programming fundamentals
- Core ML concepts

### 2. **Practical Implementation**
- Interactive notebooks for experimentation
- Code examples for all concepts
- Real-world project templates

### 3. **Reinforcement Learning**
- Practice questions with solutions
- Progressive difficulty levels
- Project-based learning

### 4. **Interview Preparation**
- Technical interview questions
- System design challenges
- Behavioral interview guidance

## Usage Examples

### Exploring Concepts

```python
# Load a specific module
import sys
sys.path.append('/path/to/genai-ml-dl-journey')

# Import ML utilities
from src.ml.utils import prepare_data
from src.nn.models import create_transformer

# Use notebook examples
# Notebooks are available for interactive learning
# In Jupyter: %load examples/introduction.ipynb
```

### Running Projects

```bash
# Run a specific proof-of-concept
cd /path/to/genai-ml-dl-journey/07-pocs/01-rag-document-assistant
python main.py --config config.yaml

# Test a module
pytest tests/test_module.py

# Build documentation
mkdocs build --strict
```

## Community and Contribution

### Contributing
1. Fork the repository
2. Create a feature branch
3. Follow commit conventions
4. Run tests before committing
5. Update documentation as needed

### Code of Conduct
This project follows responsible AI practices:
- **Bias mitigation**: Regular model audits
- **Privacy**: Offline processing where possible
- **Safety**: Content filtering and moderation
- **Transparency**: Documentation of methodologies

### Support
- Issues: GitHub issue tracker
- Questions: Stack Overflow with [genai-ml-dl-journey] tag
- Discussions: GitHub Discussions

## Project Roadmap

### Current Focus (Weeks 1-6)
- [x] Setup and initialization
- [x] Core ML pipeline
- [x] Deep learning fundamentals

### Next Phase (Weeks 7-12)
- [ ] Generative AI integration
- [ ] Mobile deployment
- [ ] Production-ready projects

### Future Enhancements
- Multi-agent systems
- Edge computing optimizations
- Real-time inference services

## License

MIT License. See LICENSE file for details.

---

*This repository is a living document of continuous learning. Contributions and feedback are welcome to help improve the learning experience for everyone.*

Co-authored by: Claude Code <noreply@anthropic.com>