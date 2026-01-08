# Gemma-3-4B Financial Sentiment Fine-Tuning

Fine-tune and deploy **google/gemma-3-4b-it** for financial sentiment analysis on AWS SageMaker using QLoRA (PEFT).

**Model:** [google/gemma-3-4b-it](https://huggingface.co/google/gemma-3-4b-it)  
**Dataset:** [Josephgflowers/Finance-Instruct-500k](https://huggingface.co/datasets/Josephgflowers/Finance-Instruct-500k)  
**Training:** PEFT QLoRA (4-bit quantization with LoRA adapters)  
**Instance:** ml.g5.2xlarge

## Notebooks

1. `01_data_analysis.ipynb` - Load and explore the dataset, prepare training/validation subsets
2. `02_finetune_training.ipynb` - Launch SageMaker training job with QLoRA
3. `03_deploy_and_evaluate.ipynb` - Deploy endpoint and evaluate with accuracy, precision, recall, F1-score 