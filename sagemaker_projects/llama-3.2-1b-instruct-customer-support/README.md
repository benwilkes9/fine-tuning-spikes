# Customer Support Ticket → Internal Bug Report Fine-Tuning PoC

Fine-tune and deploy `meta-llama/Llama-3.2-1B-Instruct` on AWS SageMaker using PEFT LoRA.

**Model:** [meta-llama/Llama-3.2-1B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct)  
**Training:** PEFT LoRA  
**Training Instance:** ml.g5.xlarge (A10G 24GB)  
**Inference Instance:** ml.g4dn.xlarge (T4 16GB)

## Use Case 
Demonstrates how fine-tuning a small language model can embed domain-specific and internal company knowledge that base models cannot access. 

The model learns to transform unstructured customer support tickets into structured internal bug reports with correct severity classification (P1/P2/P3), team routing (Auth Team, Data Platform Team), probable cause analysis, and investigation steps referencing internal tooling (Airflow DAGs, Snowflake warehouses, Redis session stores, internal scripts, Slack channels).  This showcases how small models deployed in secure private environments can outperform larger general models on specialised tasks, providing a foundation for agentic architectures that triage, route, and potentially auto-resolve support issues.

## Dataset
72 synthetic customer support tickets generated in collaboration with Claude Opus 4.5, spanning multiple categories (Data Platform, Auth, Crossover issues, etc.) with P1/P2/P3 severity levels (12 samples per category).

**Note:** This is a demo project. The training script automatically performs a 90/10 train/eval split (~65 train, ~7 eval). Notebook 03 creates an additional test set with 6 samples (1 per category) from the original source data for evaluation. The model is intentionally overfitted to demonstrate how a small fine-tuned model can learn domain-specific knowledge and internal tooling references.

## Notebooks

1. `01_finetune_training.ipynb` - Format the source data and run the fine-tuning training job on SageMaker using all 72 samples (automatically split 90/10 for train/eval).
2. `02_deploy.ipynb` - Deploy the fine-tuned model to a SageMaker endpoint with a quick sanity check.
4. `03_demo.ipynb` - Compare the base model (MLX local inference) vs the fine-tuned model (SageMaker endpoint) on customer support ticket triage.