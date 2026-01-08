# Fine-Tuning Spikes

Proof of concept experiments for LLM fine-tuning using different platforms.

## Structure

```
├── mlx_projects/       # Local fine-tuning with Apple MLX (Apple Silicon)
├── sagemaker_projects/ # AWS SageMaker fine-tuning
├── examples/           # Reference examples and notebooks (gitignore)
```

## Setup

```bash
# Install dependencies
uv sync

# For MLX experiments (Apple Silicon)
uv sync --extra mlx

# For SageMaker experiments
uv sync --extra sagemaker

# Or install all extras
uv sync --all-extras
```

## Usage

Each project contains numbered Jupyter notebooks (01_data_analysis, 02_finetune_training, etc.).

```bash
uv run jupyter lab
```