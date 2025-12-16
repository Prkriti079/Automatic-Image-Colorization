# 🎨 Automatic Image Colorization Using Deep Learning

> A CNN-based encoder–decoder model that colorizes grayscale images using semantic context, trained on the COCO dataset.

---

## 🧠 Overview

This project explores the task of **automatic image colorization**, where grayscale images are converted into plausible color images using a **regression-based deep learning model**. The model is trained in the **LAB color space**, separating luminance and chrominance channels for better learning and interpretation.

📘 **Domain**: Computer Vision  
🧪 **Tech**: Python, TensorFlow/Keras, COCO Dataset  
📊 **Evaluation**: PSNR, SSIM

---

## 🛠️ Tech Stack

- **Framework**: TensorFlow/Keras  
- **Language**: Python  
- **Dataset**: COCO (Common Objects in Context)  
- **Environment**: Google Colab + local environment support

---

## 🧩 Model Architecture

The model uses a standard **encoder–decoder CNN** pipeline:
- **Encoder**: Extracts hierarchical features from luminance input
- **Decoder**: Reconstructs chrominance channels (`a` and `b`)  
- **Output Activation**: `tanh`, normalized to LAB range

---

## 📦 Dataset & Preprocessing

- Input: Grayscale images (`L` channel from LAB)
- Output: Chrominance channels (`a` and `b`)
- Image resolution: 128x128
- Normalization applied for stability

---

## 📊 Evaluation Metrics

| Metric | Description |
|--------|-------------|
| **PSNR** | Measures reconstruction accuracy |
| **SSIM** | Measures structural similarity |

Outputs are evaluated on:
- Unseen test images (qualitative)
- PSNR/SSIM metrics (quantitative)

---

## 📈 Results Snapshot

| Sample Output |
|---------------|
| Grayscale → Predicted Colorization → Ground Truth |

---

## 🧪 Experiments

- MSE loss used for chrominance prediction
- Adam optimizer with stable convergence
- Training on Google Colab with GPU

---

## 🧭 Future Directions

- Explore GANs for more vibrant outputs
- Integrate perceptual or classification-based loss functions
- Use larger semantic datasets for contextual learning

---

## 📚 Key Learnings

- How to use LAB space to separate intensity and color  
- Designing and training encoder–decoder CNNs  
- Quantitative image quality assessment  
- Balancing visual accuracy vs computational cost

---

## ▶️ Run It Yourself

```bash
# Install dependencies
pip install -r requirements.txt

# Run training
python train.py

# Run inference
python predict.py --input ./input_image.jpg
