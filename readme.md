A curated list of completely free Text-to-Speech (TTS) models with excellent Turkish support and multilingual capabilities.
No development, just a comprehensive guide to help you find the perfect free TTS solution for your needs.

## 🌟 Features
- ✅ **Completely FREE** - No costs, no subscriptions
- 🇹🇷 **Turkish-First** - High-quality Turkish voice synthesis
- 🌍 **Multilingual** - Support for 10+ languages
- 🚀 **Easy Setup** - One-command installation

## 🚀 Quick Start Guides

### Option 1: Coqui TTS

[Coqui TTS](https://github.com/coqui-ai/TTS) is a state-of-the-art deep learning toolkit for Text-to-Speech with excellent Turkish support and 1100+ language models.

```bash
pip install TTS
```

Running a multi-speaker and multi-lingual model
```python
import torch
from TTS.api import TTS

# Get device
device = "cuda" if torch.cuda.is_available() else "cpu"

# List available 🐸TTS models
print(TTS().list_models())

# Init TTS
tts = TTS("tts_models/multilingual/multi-dataset/xtts_v2").to(device)

# Run TTS
# ❗ Since this model is multi-lingual voice cloning model, we must set the target speaker_wav and language
# Text to speech list of amplitude values as output
wav = tts.tts(text="Merhaba", speaker_wav="my/cloning/audio.wav", language="tr")
# Text to speech to a file
tts.tts_to_file(text="Merhaba", speaker_wav="my/cloning/audio.wav", language="tr", file_path="output.wav")
```

### Option 2: Facebook mms-tts

This model is part of Facebook's [Massively Multilingual Speech](https://arxiv.org/abs/2305.13516) project, aiming to provide speech technology across a diverse range of languages. You can find more details about the supported languages and their ISO 639-3 codes in the [MMS Language Coverage Overview](https://dl.fbaipublicfiles.com/mms/misc/language_coverage_mms.html), and see all MMS-TTS checkpoints on the Hugging [Face Hub: facebook/mms-tts](https://huggingface.co/models?sort=trending&search=facebook%2Fmms-tts).

### Running MMS-TTS inference in Colab

In [this notebook](https://github.com/Rumeysakeskin/mms-turkish-tts/blob/main/facebook_mms_tts_turkish.ipynb), we give an example on how to run Turkish text-to-speech inference using MMS TTS models.

By default, we run inference on a GPU. 
1. Installs necessary python packages for the other sections.
2. Choose a language or and download Turkish checkpoint. (Find the ISO code for your target language [here](https://dl.fbaipublicfiles.com/mms/tts/all-tts-languages.html).)
3. Load the checkpoint.
3. Specify the sentence you want to synthesize and generate the audio.

## 🔍 Choosing the Right TTS Model

| Feature | XTTS v2 (Coqui) | Facebook MMS-TTS |
|---------|------------------|------------------|
| **Languages** | 16 languages | 1,100+ languages |
| **Turkish Support** | ⭐⭐⭐⭐⭐ Native | ⭐⭐⭐⭐ Good |
| **GPU Required** | Optional (recommended) | Optional |
| **Voice Cloning** | ✅ 6-second audio clip | ❌ No cloning |
| **Single Speaker** | ✅ Yes | ✅ Yes (per language) |
| **Multi-Speaker** | ✅ Yes | ❌ One model per language |
| **Model Size for TR** | ~1.9GB | 277.01 MB |
| **Fine-tuning** | ✅ Yes | ❌ Pre-trained only |
| **License** | Coqui Public License | CC-BY-NC 4.0 |
| **Quality** | ⭐⭐⭐⭐⭐ Excellent | ⭐⭐⭐⭐ Very Good |
| **Commercial Use** | ✅ Yes (with license) | ❌ Non-commercial only |
| **Inference Speed** | Fast | Moderate |
| **Best For** | Voice cloning, production | Research, many languages |


⭐ Star this repo to help others discover free TTS solutions!

