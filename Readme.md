---

#  Rhushya  – Reasoning Model Fine-Tuning

This project demonstrates how to fine-tune a large language model (LLM) using synthetic reasoning datasets generated with the `Faker` library. Leveraging Hugging Face and the Unsloth framework, this notebook enables efficient model training with quantization and advanced training techniques.

##  Project Structure

* `FINAL_RHUSHYA_COGNITION_LAB.ipynb`: Jupyter notebook containing all steps from setup, data generation, training, and evaluation.

## 🛠️ Setup Instructions

### 1. Install Required Libraries

Ensure your Colab environment is fresh, then run the following:

```bash
!pip install datasets pandas Faker -q
!pip install "unsloth[colab-ampere-torch230] @ git+https://github.com/unslothai/unsloth.git"
!pip install huggingface_hub bitsandbytes -q
```

>  **Important:** Restart the Colab runtime after installation.

### 2. Authenticate Hugging Face

Log in to your Hugging Face account:

```bash
!huggingface-cli login
```

### 3. Optional: Faster Installation with `uv`

```bash
!uv pip install datasets pandas Faker huggingface_hub unsloth unsloth_zoo trl transformers bitsandbytes -q
```

##  Project Workflow

###  Step 1: Generate Synthetic Reasoning Data

Using `Faker`, a dataset of custom reasoning tasks (e.g., logical, ethical, hypothetical questions) is generated. Data is stored in a Hugging Face-compatible format.

###  Step 2: Load and Prepare Model

Utilizes `Unsloth.FastLanguageModel` for loading a quantized LLM (like LLaMA or Mistral), enabling faster training.

###  Step 3: Fine-tuning with `SFTTrainer`

The model is fine-tuned using the `trl` library’s `SFTTrainer`, which supports:

* LoRA-based parameter-efficient fine-tuning
* Custom learning rate, batch size, and epoch settings

###  Step 4: Model Evaluation and Export

After training, the model is saved and optionally pushed to Hugging Face Hub for sharing or deployment.

##  Key Technologies Used

* **Hugging Face Transformers**: For model handling and training.
* **Unsloth**: Optimized and quantized training for large models.
* **Datasets**: For processing and managing training/evaluation data.
* **Faker**: For dynamic and diverse synthetic dataset creation.

##  Example Prompt Format

```
### Instruction:
John has two more apples than Mary. Mary has five apples. How many does John have?

### Response:
John has 5 + 2 = 7 apples.
```


##  Notes

* Best run in **Google Colab with GPU (A100 or T4)**.
* Dataset generation is customizable—adjust the prompt types or difficulty.
* Hugging Face token is required for uploading or downloading models.

##  License

MIT License – feel free to use, modify, and distribute with attribution.

---

Would you like this as a downloadable `README.md` file or added to the notebook itself?
