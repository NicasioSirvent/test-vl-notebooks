# VL Demo Notebooks

This repository contains demonstration notebooks for Qwen3-VL, to test locally served VL models, focused on:
- Video understanding
- OCR recognition
- Document understanding
- 2D/3D Grounding
- Mobile agents
- And more...

These notebooks are adapted from the official Qwen-VL repository, modified to test locally served and edge (phone) deployment scenarios,
and usable in any open-ai compatible end-point.

## Requirements

- Python 3.8+
- Jupyter Notebook or Jupyter Lab
- SGLang or similar inference server (OpenAI API compatible)
- Recommended: Virt Env (Conda, uv, pip... with required libraries)

## Installation

### 1. Clone the repository (if new)

```bash
git clone ...
```

### 2. Create .env file

Copy `.env.example` to `.env` and edit with your credentials:

```bash
cp .env.example .env
vim .env  # or your favorite editor
```

Then update the variables inside `.env`:

```
# Your API key (any string for local servers)
OPENAI_API_KEY="your_local_key"

# Base URL of your OpenAI-compatible server (e.g., SGLang)
OPENAI_BASE_URL="http://localhost:30000/v1"

# Model name to use
MODEL_ID="qwen3.5"
```

## Running the Notebooks

### Option 1: VS Code
Recommended, VS Code supports notebooks natively.


### Option 2: Traditional Jupyter Notebook

```bash
jupyter notebook
```

Then open `video_understanding.ipynb` or other notebooks in your browser.

### Option 3: Jupyter Lab

```bash
jupyter lab
```

### Option 4: Execution from terminal

```bash
jupyter nbconvert --to notebook --execute video_understanding.ipynb --output video_understanding_executed.ipynb
```

## Available Notebooks

| Notebook | Description |
|----------|-------------|
| `video_understanding.ipynb` | Video analysis and understanding |
| `ocr.ipynb` | OCR recognition with Qwen3-VL |
| `spatial_understanding.ipynb` | Spatial understanding and 2D grounding |
| `2d_grounding.ipynb` | 2D object localization |
| `3d_grounding.ipynb` | 3D object localization |
| `document_parsing.ipynb` | Document analysis and parsing |
| `long_document_understanding.ipynb` | Long document understanding |
| `omni_recognition.ipynb` | Multimodal recognition |
| `mobile_agent.ipynb` | Mobile agents |
| `think_with_images.ipynb` | Image-based reasoning |
| `mmcode.ipynb` | mmcode interaction |
| `computer_use.ipynb` | Computer usage |

## Environment Variables

| Variable | Required | Description | Default |
|----------|----------|-------------|---------|
| `OPENAI_API_KEY` | Yes | API key for OpenAI-compatible server | - |
| `OPENAI_BASE_URL` | Yes | Base URL of the server (SGLang, etc.) | - |
| `MODEL_ID` | Yes | Model name (e.g., qwen3.5) | - |


## Security

- ✅ `.env` is in `.gitignore` - never uploaded to GitHub
- ✅ `*.env` files are excluded
- ⚠️ **NEVER commit** real credentials

## Troubleshooting

### "KeyError: 'OPENAI_API_KEY'"

Make sure you have a `.env` file with variables configured:

```bash
cp .env.example .env
# Edit .env
pip install python-dotenv
```

### "No module named 'dotenv'"

Install python-dotenv:

```bash
pip install python-dotenv
```

### Connection failed to server

Verify that:
1. The inference server is running
2. The URL in `OPENAI_BASE_URL` is correct
3. The port is not blocked by firewall


## Resources

- [Qwen-VL Official Documentation](https://qwen.readthedocs.io/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference/)
