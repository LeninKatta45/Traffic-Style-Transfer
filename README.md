# 🚦 Traffic Style Transfer – Night to Day using CycleGAN

This project implements a **CycleGAN** model to transform **night-time traffic images** into **day-time traffic images** and vice versa, without the need for paired datasets. The model learns style mappings between two domains (Night ↔ Day) while preserving content.

![CycleGAN Concept](https://raw.githubusercontent.com/junyanz/CycleGAN/master/imgs/horse2zebra.gif)

---

## 📌 Features
- **Unpaired Image-to-Image Translation** using CycleGAN
- **Night ↔ Day Traffic Scene Transformation**
- **ResNet-based Generator** with Instance Normalization
- **PatchGAN Discriminator**
- Cycle-consistency & Identity Loss for content preservation
- Saves models periodically and generates visual results

---

## 🏗 Architecture

The project follows the **CycleGAN** architecture:

Night Image → G_AtoB → Day Image
Day Image → G_BtoA → Night Image

Two **Generators**:
- `G_AtoB`: Night → Day
- `G_BtoA`: Day → Night

Two **Discriminators**:
- `D_A`: Distinguishes real night from fake night images
- `D_B`: Distinguishes real day from fake day images

Losses:
- **Adversarial Loss**
- **Cycle-Consistency Loss**
- **Identity Loss**

---

## 📂 Dataset

This project uses the **Night2Day Traffic dataset**, which contains:
- `trainA/` – Night images
- `trainB/` – Day images

You can replace it with your own unpaired dataset.

---

## ⚙️ Installation

# Clone this repository
git clone https://github.com/yourusername/traffic-style-transfer.git
cd traffic-style-transfer

# Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate   # On Windows use: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
# requirements.txt should include:
tensorflow
keras
numpy
matplotlib
Pillow
