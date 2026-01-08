# Gemma 

This folder contains notebooks that are used to finetune and test inference on local MacBook Pro M4 Max using the model mlx-community/gemma-3-270m-it-bf16 and the dataset Josephgflowers/Finance-Instruct-500k

Model card: [mlx-community/gemma-3-270m-it-bf16 on Hugging Face](https://huggingface.co/mlx-community/gemma-3-270m-it-bf16)

Data set: [Josephgflowers/Finance-Instruct-500k on Hugging Face](https://huggingface.co/datasets/Josephgflowers/Finance-Instruct-500k)

There are three notebooks:

1. `01_data_analysis.ipynb` - Analyse the source dataset and produce a subset of data for fine-tuning.
2. `02_finetune_training.ipynb` - Run the fine-tuning training job with LoRA.
3. `03_evaluation.ipynb` - Evaluate the fine-tuned model against the base model on the test set.
