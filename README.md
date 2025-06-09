
# Plant Species Image Classification

This project involves building a deep learning model using **MobileNetV2** to classify images of different plant species. It includes data preprocessing, training with callbacks, evaluation, and annotation generation.

---

## 📁 Project Structure

```
plant_proj/
│
├── input_data/                # Contains subfolders for each plant species
│   ├── neem_tree/
│   ├── banana_plant/
│   └── aloe_vera/
│
├── annotations.csv            # Generated CSV with image paths and labels
├── mobilenetv2_base_model.h5  # Base model loaded for training
├── best_model.h5              # Best model saved via checkpoint
├── model_training.ipynb       # Jupyter notebook for training and evaluation
├── generate_annotations.py    # Script to generate annotations.csv
└── README.md                  # This file
```

---

## 🧠 Model

- **Architecture**: MobileNetV2 (pretrained on ImageNet)
- **Input Size**: 224x224 RGB
- **Loss Function**: Categorical Crossentropy
- **Optimizer**: Adam
- **Callbacks**: EarlyStopping, ModelCheckpoint

---

## 🚀 How to Run

1. **Prepare the Dataset**  
   Structure your dataset as:

   ```
   input_data/
       class_1/
           img1.jpg
           img2.jpg
       class_2/
           img1.jpg
           ...
   ```

2. **Generate Annotations**  
   Run the provided script to create a CSV:

   ```bash
   python generate_annotations.py
   ```

3. **Train the Model**  
   Use the notebook `model_training.ipynb` to load the base model and begin training.

4. **Evaluate**  
   Use validation accuracy and loss logs to assess model performance. Visual inspection using sample plots is included in the notebook.

---

## 📊 Example Annotation (CSV)

| filename               | label         |
|------------------------|---------------|
| neem_tree/img1.jpg     | neem_tree     |
| banana_plant/img2.jpg  | banana_plant  |

---

## 💡 Notes

- All images are renamed to `.jpg` with unique names to avoid clashes.
- Training uses early stopping to prevent overfitting.
- Legacy HDF5 format (`.h5`) is used for compatibility, though `.keras` is recommended.

---

## 📌 Requirements

- Python 3.8+
- TensorFlow 2.19
- Keras
- Pillow
- Matplotlib
- Pandas
