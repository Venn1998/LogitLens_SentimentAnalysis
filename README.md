# Logit Lens Exploration on Sentiment Analysis with GPT-2

This project explores the interpretability of **GPT-2** when performing **sentiment analysis** using the **Logit Lens** technique. The **Logit Lens** allows us to inspect how predictions evolve through the model's intermediate layers, providing insights that go beyond the final output.

We evaluate different versions of **GPT-2** (small, medium, large, and distilled) in **zero-shot, one-shot, and few-shot classification** settings, using datasets like **SST-2** and **IMDB**. Additionally, we analyze the effect of **fine-tuning GPT-2** on sentiment classification and investigate **overthinking**—a phenomenon where models revise initially correct predictions into incorrect ones throughout the layers. 

## Project Overview

### Goals
- Understand how **GPT-2 processes sentiment classification** at different layers.
- Use **Logit Lens** to visualize **prediction trajectories**.
- Compare the performance of **pre-trained vs. fine-tuned** models.
- Analyze how **incorrect demonstrations** affect model confidence.
- Investigate **overthinking** in different GPT-2 variants.

### Key Techniques
- **Logit Lens:** Extracts and visualizes predictions from **intermediate layers** of GPT-2.
- **Zero-shot / One-shot / Few-shot learning:** Evaluates model performance with minimal supervision.
- **Fine-tuning GPT-2:** Trains the model for sentiment classification on IMDB data.
- **Hook-based layer inspection:** Captures intermediate model states during forward passes.

The **entire project is implemented in the Jupyter notebook** `experiments.ipynb`. This notebook contains:
1. **Data Preprocessing:** Formatting SST-2 and IMDB data for sentiment classification.
2. **Logit Lens Implementation:** Extracting and visualizing intermediate layer predictions.
3. **Zero-shot Analysis:** Evaluating GPT-2 without fine-tuning.
4. **One-shot & Few-shot Experiments:** Investigating model behavior with example demonstrations.
5. **Fine-tuning GPT-2:** Training on IMDB for improved performance.
6. **Overthinking Analysis:** Checking whether models revise correct predictions due to misleading prompts.
7. **Visualization of Prediction Trajectories:** Heatmaps of token predictions across layers.

🔍 Key Findings
- GPT-2 (pre-trained) performs poorly in zero-shot sentiment classification.
- Fine-tuning improves accuracy significantly, stabilizing predictions in earlier layers.
- Intermediate layers sometimes predict the correct label, but the final layer can override it.
- Incorrect examples reduce model confidence, making predictions less stable.
- GPT-2-large exhibits signs of overthinking, sometimes revising correct intermediate predictions into incorrect ones.
- DistilGPT-2 behaves unpredictably, sometimes being more confident with incorrect examples.


