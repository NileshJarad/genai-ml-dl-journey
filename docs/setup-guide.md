# Setup Guide

## Prerequisites

- Python 3.10+
- Git
- Virtual environment tool (venv, conda, or poetry)

## Installation

### Using pip

```bash
# Clone the repository
git clone <repo-url>
cd genai-ml-dl-journey

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Install development dependencies
pip install -e ".[dev]"
```

### Using conda

```bash
# Create conda environment
conda create -n genai-ml python=3.10
conda activate genai-ml

# Install dependencies
pip install -r requirements.txt
```

### Using Poetry

```bash
# Install poetry (if not already installed)
curl -sSL https://install.python-poetry.org | python3 -

# Install dependencies
poetry install
```

## IDE Configuration

### VS Code

1. Install Python extension
2. Set Python interpreter to venv
3. Enable Pylance type checking
4. Configure formatting on save (Black)
5. Install recommended extensions:
   - Jupyter
   - Pylance
   - Black Formatter
   - Ruff
   - GitLens

### PyCharm

1. Open project folder
2. Configure Project Interpreter → Add Virtual Environment
3. Enable Type Checking
4. Configure Code Style → Python → PEP 8

## Environment Variables

```bash
# Copy example and edit
cp .env.example .env

# Edit with your API keys
# OPENAI_API_KEY=your-key
# ANTHROPIC_API_KEY=your-key
# etc.
```

## Jupyter Notebooks

```bash
# Start Jupyter Lab
jupyter lab

# Or start classic notebook
jupyter notebook
```

## Running Tests

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=src --cov-report=html

# Run specific test file
pytest tests/test_specific.py -v
```

## Pre-commit Hooks

```bash
# Install pre-commit
pip install pre-commit

# Install hooks
pre-commit install

# Run manually
pre-commit run --all-files
```

## Docker (Optional)

```bash
# Build image
docker build -t genai-ml-dl-journey .

# Run container
docker run -it --rm genai-ml-dl-journey
```

## Troubleshooting

### Common Issues

1. **Import errors**: Ensure venv is activated and packages installed
2. **CUDA issues**: Install PyTorch with correct CUDA version
3. **Memory issues**: Use smaller batch sizes or gradient accumulation
4. **API rate limits**: Implement exponential backoff and caching

### Getting Help

- Check existing issues in GitHub
- Review documentation in `docs/`
- Ask in discussions or team channels