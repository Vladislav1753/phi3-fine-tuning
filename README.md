## 🧠 LLM Fine-Tuning with Unsloth (QLoRA) in Colab

This project demonstrates how to fine-tune a large language model using [Unsloth](https://github.com/unslothai/unsloth) and QLoRA on a custom dataset. The training is performed inside Google Colab using 4-bit quantization for memory efficiency.

## 📁 Files

- `fine_tuning_colab.ipynb`: Main Colab notebook containing the full training pipeline.
- `json_extraction_dataset_500.json`: Custom dataset in JSON format, structured with `"input"`, and `"output"` fields.

## 📚 Dataset Format

Each example in the dataset is structured like this:

```json
  {
    "input": "Extract the product information:\n<div class='product'><h2>iPad Air</h2><span class='price'>$1344</span><span class='category'>audio</span><span class='brand'>Dell</span></div>",
    "output": {
      "name": "iPad Air",
      "price": "$1344",
      "category": "audio",
      "manufacturer": "Dell"
    }
  }
````

## 🛠️ Features

* ✅ Supports 4-bit quantized model loading
* ✅ Uses `SFTTrainer` from `trl`
* ✅ Efficient training using LoRA adapters

## 💾 Saving the Model

After training, the model is saved in GGUF format for download from Colab.

## 🚀 Getting Started

To reproduce the training:

1. Open the Colab notebook
2. Upload your dataset
3. Run the cells sequentially

No special hardware or setup is needed beyond a Colab GPU runtime.

## 📦 Model Format

The final model is saved in:

* `gguf_model/`: Directory containing quantized GGUF weights

## 🧩 Requirements

These libraries are installed inside Colab:

* `unsloth`
* `transformers < 0.9.0`
* `trl`
* `bitsandbytes`
* `xformers < 0.0.27`
