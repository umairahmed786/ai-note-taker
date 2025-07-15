# 🏛️ Denver Council Meeting Minutes Extractor

This project extracts and summarizes official city council meeting transcriptions using **OpenAI Whisper**, **LLMs** (like LLaMA 3), and **transformers**. It produces structured meeting minutes in markdown format, including summaries, discussion points, key takeaways, and action items with owners.

## 📌 Features

- ✅ **Automatic Transcription** from `.mp3` files using `whisper-1` via OpenAI.
- ✅ **Summary & Minutes Generation** using LLaMA 3 (`meta-llama/Meta-Llama-3.1-8B-Instruct`).
- ✅ Generates **Markdown-formatted meeting minutes** with:
  - Summary (location, date, attendees)
  - Key discussion points
  - Takeaways
  - Action items with responsible members
- ✅ Uses `BitsAndBytes` for 4-bit quantization of large models.
- ✅ Supports **Google Drive integration** for audio input.

## 🧠 Models Used

| Task                         | Model                                               |
|-----------------------------|-----------------------------------------------------|
| Audio transcription         | `whisper-1` (via OpenAI API)                        |
| Minutes generation (LLM)    | `meta-llama/Meta-Llama-3.1-8B-Instruct`             |
| Embedding support (optional)| `Qwen/Qwen3-Embedding-0.6B`                         |

## 🚀 Quick Start (Google Colab)

1. Clone or upload the notebook to [Google Colab](https://colab.research.google.com).
2. Install dependencies:
   ```python
   !pip install -q requests bitsandbytes==0.46.0 transformers==4.48.3 accelerate==1.3.0 openai
3. Add Your API Keys (OpenAI + Hugging Face)
   ```python
   from google.colab import userdata
   openai_api_key = userdata.get("OPENAI_API_KEY")
   hf_token = userdata.get("HF_TOKEN")
4. Generate Meeting Minutes with LLaMA
   ```python
   response = model.generate(
    inputs,
    max_new_tokens=2000,
    streamer=streamer
    )
## 📖 Example Output

## Minutes of Denver City Council Meeting

**Date:** October 9th, 2017  
**Location:** Denver City Council Chambers  
**Attendees:** Councilman Lopez, Councilwoman Ortega, ...

### Summary
...

### Key Discussion Points
- Importance of Indigenous Peoples Day
- Cultural preservation and environmental defense
...

### Action Items
- Councilman Lopez: Promote education about Indigenous history
...

