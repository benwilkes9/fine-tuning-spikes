# Customer Support Ticket → Internal Bug Report Fine-Tuning PoC

This folder contains notebooks that are used to finetune and test inference on local MacBook Pro M4 Max using the model `meta-llama/Llama-3.2-1B-Instruct`

Model Card: [meta-llama/Llama-3.2-1B-Instruct on Hugging Face](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct)

## Use Case 
Demonstrates how fine-tuning a small language model can embed domain-specific and internal company knowledge that base models cannot access. 

The model learns to transform unstructured customer support tickets into structured internal bug reports with correct severity classification (P1/P2/P3), team routing (Auth Team, Data Platform Team), probable cause analysis, and investigation steps referencing internal tooling (Airflow DAGs, Snowflake warehouses, Redis session stores, internal scripts, Slack channels).  This showcases how small models deployed in secure private environments can outperform larger general models on specialised tasks, providing a foundation for agentic architectures that triage, route, and potentially auto-resolve support issues.

## Dataset
This contains synthetic data I generated in collaboration with Claude Opus 4.5.

## Notebooks
There are two notebooks:

1. `01_finetune_training.ipynb` - Split the source data into train, validate and test, and run the fine-tuning training job with LoRA.
2. `02_evaluation.ipynb` - Compare fine-tuned model vs base model outputs. Configurable to evaluate on test set or training samples (defaults to training samples to demonstrate fine-tuning effect).
