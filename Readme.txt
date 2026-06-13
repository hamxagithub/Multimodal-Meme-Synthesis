AI Meme Generator
Text OR Image → Meme | BLIP-2 + Mistral-7B | Saves Models → Deploy on HuggingFace Spaces

---

Step 0 — Add These Kaggle Datasets First!

Before running: go to **Notebook Settings → Add Data** and search + add each one:

| # | Dataset | Kaggle Link to Add | Path Inside Notebook |
|---|---------|-------------------|----------------------|
| 1 | Memotion 7K (memes + labels) | `williamscott701/memotion-dataset-7k` | `/kaggle/input/memotion-dataset-7k/` |
| 2 | Reddit Memes (images + metadata) | `sayangoswami/reddit-memes-dataset` | `/kaggle/input/reddit-memes-dataset/` |
| 3 | Meme Templates (blank templates) | `gmorinan/meme-templates` | `/kaggle/input/meme-templates/` |

Direct Kaggle Dataset URLs:
https://www.kaggle.com/datasets/williamscott701/memotion-dataset-7k
https://www.kaggle.com/datasets/sayangoswami/reddit-memes-dataset
https://www.kaggle.com/datasets/gmorinan/meme-templates

 Models Used
| Task | Model | Size |
|------|-------|------|
| Image → Caption | `Salesforce/blip2-opt-2.7b` | ~6 GB VRAM |
| Text → Meme Text | `mistralai/Mistral-7B-Instruct-v0.2` (4-bit) | ~5 GB VRAM |
| Template Matching | TF-IDF on Kaggle dataset | CPU |

Output for HuggingFace Deployment
Everything saved to `/kaggle/working/meme_model_export/`:

meme_model_export/
├── blip2/               ← BLIP-2 weights + processor
├── caption_model/       ← Mistral tokenizer + weights
├── meme_templates.json  ← Template metadata
├── app.py               ← Gradio app (ready to upload)
├── requirements.txt     ← HF Space dependencies
└── README.md            ← HF Space config
