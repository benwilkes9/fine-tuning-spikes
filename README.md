# Fine-Tuning Spikes

Proof of concept experiments for LLM fine-tuning.

## Structure

```
├── mlx_projects/       # Local fine-tuning with Apple MLX (Apple Silicon)
├── sagemaker_projects/ # AWS SageMaker fine-tuning
├── examples/           # Reference examples and notebooks (gitignore)
```

## Setup

```bash
# Install all dependencies (MLX + SageMaker)
uv sync
```

## Usage

Each project contains numbered Jupyter notebooks, for example:

- `01_data_analysis.ipynb` - Load and explore dataset
- `02_finetune_training.ipynb` - Fine-tune the model
- `03_deploy_and_evaluate.ipynb` - Deploy and evaluate

```bash
uv run jupyter lab
```