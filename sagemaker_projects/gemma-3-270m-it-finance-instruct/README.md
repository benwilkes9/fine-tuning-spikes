# Gemma-3-270M Financial Sentiment Fine-Tuning

Fine-tune and deploy **google/gemma-3-270m-it** for financial sentiment analysis on AWS SageMaker using PEFT LoRA.

**Model:** [google/gemma-3-270m-it](https://huggingface.co/google/gemma-3-270m-it)  
**Dataset:** [Josephgflowers/Finance-Instruct-500k](https://huggingface.co/datasets/Josephgflowers/Finance-Instruct-500k)  
**Training:** PEFT LoRA  
**Training Instance:** ml.g5.xlarge (A10G 24GB)  
**Inference Instance:** ml.g4dn.xlarge (T4 16GB)

## Notebooks

1. `01_data_analysis.ipynb` - Load and explore the dataset, prepare training/validation subsets
2. `02_finetune_training.ipynb` - Launch SageMaker training job with LoRA
3. `03_deploy_and_evaluate.ipynb` - Deploy endpoint and evaluate with accuracy, precision, recall, F1-score
4. `04_compare_sagemaker_vs_mlx.ipynb` - Compare SageMaker vs MLX fine-tuning results