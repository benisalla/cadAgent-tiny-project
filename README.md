# CadQuery Code Generator

This project generates **CadQuery Python code** from **2D CAD images**. The goal is to teach a model to look at a shape and write the code that recreates it.

---

## What I did

* Used the **GenCAD dataset** (images + code pairs).
* Built a model with:

  * **ResNet18** to understand the image.
  * A small **Transformer decoder** to write the code.
* Trained and evaluated the model using:

  * **Syntax check** (does the code run?)
  * **Shape comparison** using **IOU**.
* Logged and visualized everything inside the notebook.

📓 All steps are in: [`good_luck.ipynb`](./good_luck.ipynb)

---

## How to build the environment for the notebook to live in :)

```bash
python -m venv .venv
source ./.venv/Scripts/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

---

## Models I used

* **Encoder**: ResNet18
* **Decoder**: Transformer (like GPT)
* Trained with cross-entropy loss
* Generates code token by token

---

## I respected the same evaluation you gave, even though this type of evaluation is hard at the first stages of training or fine-tuning because it is always 0.0

* **VSR**: how many codes run without error
* **IOU\_best**: how close the predicted shape is to the original
