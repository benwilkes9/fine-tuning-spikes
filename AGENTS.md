# Agents Instructions

- Purpose: proof-of-concept LLM fine-tuning on Apple Silicon (MLX) and AWS SageMaker; workflows are mostly Jupyter notebooks.
- Setup: Python ≥3.10; install with `uv sync`, launch with `uv run jupyter lab`. AWS creds (and optional HF token) must be available in env or `.env` (python-dotenv is included).
- Layout (patterns):
  - `mlx_projects/<model>-<task>/`: Local MLX runs; numbered notebooks `01_*`→`0N_*`; configs (e.g., `lora_config.yaml`), adapters under `adapters/`, optional data snapshots under `data/`.
  - `sagemaker_projects/<model>-<task>/`: SageMaker pipelines; notebooks `01_*`→`0N_*` (data → train → deploy/eval → compare); helper code under `sagemaker_code/`, cached data under `tmp_cache_local_dataset/`, results CSVs nearby.
  - `examples/`: Mostly read-only AWS samples; contains `amazon-sagemaker-generativeai` (large reference) and `mlx/` guidance.
  - Utility notebooks like `cleanup_sagemaker_resources.ipynb` live at the project root or within `sagemaker_projects/`.
- Conventions: Ruff (E,F,I) with 100-char lines; `uv` manages deps (`pyproject.toml`/`uv.lock`). Avoid committing large artifacts; notebooks are numbered sequentially—keep ordering intact.
