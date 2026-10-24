# Coding Standards

## Python Style Guide

### Formatting

- Use **Black** for code formatting (line length: 88)
- Use **Ruff** for linting and import sorting
- Use type hints for all function signatures

```python
# Good
def train_model(
    model: nn.Module,
    train_loader: DataLoader,
    optimizer: Optimizer,
    config: TrainingConfig,
) -> TrainingMetrics:
    ...

# Avoid
def train_model(model, train_loader, optimizer, config):
    ...
```

### Naming Conventions

- **Classes**: PascalCase (`ModelTrainer`, `DataProcessor`)
- **Functions/Methods**: snake_case (`train_epoch`, `compute_loss`)
- **Variables**: snake_case (`learning_rate`, `batch_size`)
- **Constants**: UPPER_SNAKE_CASE (`MAX_EPOCHS`, `DEFAULT_LR`)
- **Private**: Leading underscore (`_internal_method`)
- **Type variables**: PascalCase with suffix (`T_co`, `ModelType`)

### Docstrings

Use Google-style docstrings for all public functions/classes:

```python
def train_model(
    model: nn.Module,
    train_loader: DataLoader,
    optimizer: Optimizer,
    config: TrainingConfig,
) -> TrainingMetrics:
    """Train the model for one epoch.

    Args:
        model: The neural network model to train.
        train_loader: DataLoader providing training batches.
        optimizer: Optimizer for parameter updates.
        config: Training configuration parameters.

    Returns:
        TrainingMetrics containing loss, accuracy, and timing info.

    Raises:
        ValueError: If config contains invalid parameters.
    """
    ...
```

## ML Code Conventions

### Data Handling

- Use `torch.utils.data.Dataset` and `DataLoader` for PyTorch
- Use `tf.data.Dataset` for TensorFlow
- Always separate train/validation/test splits
- Use `sklearn.model_selection` for cross-validation

```python
# Good: Explicit splits with fixed seeds
train_df, test_df = train_test_split(
    df, test_size=0.2, random_state=42, stratify=df["label"]
)
```

### Model Definition

- Define models as classes inheriting from `nn.Module` or `tf.keras.Model`
- Use config classes/dataclasses for hyperparameters
- Separate architecture from training logic

```python
@dataclass
class ModelConfig:
    hidden_size: int = 256
    num_layers: int = 4
    dropout: float = 0.1

class TransformerModel(nn.Module):
    def __init__(self, config: ModelConfig):
        super().__init__()
        self.config = config
        # ...
```

### Training Loops

- Use clear epoch/batch structure
- Log metrics consistently (wandb, tensorboard, or custom)
- Handle device placement explicitly
- Use mixed precision when appropriate

```python
for epoch in range(config.epochs):
    model.train()
    for batch in train_loader:
        batch = {k: v.to(device) for k, v in batch.items()}
        optimizer.zero_grad()
        loss = model(**batch).loss
        loss.backward()
        optimizer.step()
```

### Experiment Tracking

- Log hyperparameters, metrics, and artifacts
- Use consistent naming for experiments
- Version datasets and model checkpoints

## Testing Requirements

### Unit Tests

- Test pure functions and utilities
- Test model forward pass with dummy data
- Test data preprocessing pipelines
- Mock external dependencies (APIs, databases)

```python
def test_compute_loss():
    """Test loss computation with known values."""
    logits = torch.tensor([[2.0, 1.0], [0.5, 1.5]])
    labels = torch.tensor([0, 1])
    loss = compute_loss(logits, labels)
    assert loss.item() == pytest.approx(0.1269, rel=1e-3)
```

### Integration Tests

- Test end-to-end training for 1-2 epochs
- Test model save/load cycle
- Test inference pipeline

### Test Organization

```
tests/
├── unit/
│   ├── test_data.py
│   ├── test_models.py
│   └── test_utils.py
├── integration/
│   ├── test_training.py
│   └── test_inference.py
└── fixtures/
    └── sample_data.csv
```

## Documentation Standards

### README Requirements

Every project/module must have a README with:
- Purpose and scope
- Installation/usage instructions
- Key dependencies
- Example usage
- Links to detailed docs

### Code Comments

- Explain **why**, not **what** (code shows what)
- Document complex algorithms or non-obvious decisions
- Use `# TODO:` and `# FIXME:` for known issues

### Type Hints

- Required for all public APIs
- Use `from __future__ import annotations` for forward references
- Use `Protocol` for structural typing
- Prefer `Sequence` over `List`, `Mapping` over `Dict` in signatures

## Git Workflow

### Branching

- `main`: Production-ready code
- `develop`: Integration branch
- `feature/*`: New features
- `fix/*`: Bug fixes
- `experiment/*`: Research/exploration

### Commit Messages

```
type(scope): short description

Longer description if needed

Fixes #123
```

Types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`, `perf`

### Pull Requests

- Require 1+ approval for `main`
- Pass all CI checks
- Include tests for new features
- Update documentation
- Squash commits before merge

## Performance Guidelines

- Profile before optimizing
- Use vectorized operations (avoid Python loops)
- Leverage GPU/TPU when available
- Use appropriate batch sizes
- Consider mixed precision training
- Cache expensive computations

## Security

- Never commit secrets or API keys
- Use environment variables for configuration
- Validate all external inputs
- Sanitize file uploads
- Use dependency scanning (dependabot, safety)