# Consistency Distillation of Stable Diffusion 1.5 for Fast Image Generation

This project was completed as part of CV-week (YSDA). The goal was to implement *Consistency Distillation* to accelerate image generation using *Stable Diffusion 1.5* by distilling the original multi-step diffusion process into a 4-step student model while maintaining high image quality.

### **Project Overview:**
- Implemented **Consistency Distillation** for Stable Diffusion 1.5 to reduce inference steps from 50 to 4, ensuring efficient image generation.
- Utilized a subset of the COCO dataset (5000 text-image pairs) to train the distilled model under limited computational resources.
- Integrated **LoRA adapters** for memory-efficient fine-tuning.
- Developed core diffusion operations:
  - **DDIM solver step** for generating images at different time steps.
  - **Noise sampling process** for image degradation and training.
- Trained the model to enforce **self-consistency**, ensuring predictions from different diffusion steps align, with boundary conditions to prevent degenerate solutions.
- Explored analytical approximations for adjacent points in the diffusion trajectory, improving efficiency without teacher model reliance.
- Utilized Hugging Face libraries: `diffusers`, `transformers`, `peft`, and `accelerate` for model management, optimization, and deployment.
