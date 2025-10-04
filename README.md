Self-supervised **masked reconstruction** on webcam frames using a tiny JEPA setup:
- **ConvEncoder (student/teacher)** with EMA
- **JEPA PatchPredictor** (MLP head)
- **Decoder** conditioned on the masked RGB
- **Edge (Laplacian) loss** for sharper fills

The script supports **collecting frames**, **training** (JEPA pretrain → decoder), **live demo** on webcam, and **single-image testing**, without external datasets.

---

## What it does
- Randomly **masks a block** in each image.
- Learns latent prediction with **JEPA** (student vs. EMA teacher).
- Trains a light decoder to **fill the masked region**.
- Encourages crisp details via **edge loss** and **ring consistency** around the mask.

---
