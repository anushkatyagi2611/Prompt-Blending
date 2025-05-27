# 🧪 Prompt Blending Project

> "Where two ideas meet, magic happens."

For example, see some of our generated images in this folder:  
[_sample outputs on Google Drive_](https://drive.google.com/drive/folders/1Qr7L0ED3cmgXQ8kRzTRzSJYbFwuRDTD9?usp=drive_link)

---

## 🎯 Welcome

**Prompt Blending Project** is a playful yet powerful toolkit that turns two simple text prompts into a single, visually compelling image. By combining the strengths of **Groq’s ChatGroq**, **OpenCLIP**, and **Stable Diffusion v1.5**, we blend your ideas seamlessly—whether it’s 🍰 + ❄️ or 🚀 + 🎨.

---

## 🚀 Features

- **Prompt Enhancement**: Transforms your plain prompts into rich, descriptor-filled instructions using Groq’s Llama3-70B (temperature = 0.3).
- **Token Weighting**: Emphasizes the main subjects (e.g., `(snow:1.7)`) while toning down secondary details (e.g., `(cake:1.1)`).
- **Embedding Blending**: Uses linear interpolation `(α·emb_a + (1–α)·emb_b)` over a balanced alpha range (0.4–0.6) to capture both prompts fairly.
- **Aesthetic Scoring**: Harnesses CLIP cosine similarity against an "aesthetic prompt" list to pick the most pleasing blend.
- **Reproducibility**: Fixed random seed (42) and mixed-precision (`float16`, `autocast`) ensure consistent, efficient image generation.
- **Interactive Demo**: Spin up a Gradio interface in seconds and watch your prompts come to life.

---

## 💡 How It Works

1. **Input** two text prompts.  
2. **Enhance** them via ChatGroq to add lighting, mood, and composition hints.  
3. **Tokenize** and **encode** each enhanced prompt with OpenCLIP.  
4. **Interpolate** embeddings across 20 finely spaced α values between 0.4 and 0.6.  
5. **Generate** an image for each blend using Stable Diffusion v1.5.  
6. **Score** each image with CLIP’s image and text encoders (cosine similarity).  
7. **Select** the highest-scoring image and return it to you.

---

## 🎨 Customization & Future Ideas

- **Adaptive Alpha**: Automatically narrow down the best alpha range based on embedding similarity.  
- **Non-Linear Blending**: Explore curved or attention-guided paths through embedding space.  
- **User Feedback Loop**: Let users rate outputs and refine the aesthetic scoring mechanism.  
- **Multi-Prompt Blends**: Extend from two prompts to n-way creative mashups.
