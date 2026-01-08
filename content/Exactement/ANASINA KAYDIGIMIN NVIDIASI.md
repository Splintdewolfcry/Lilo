uv pip install torch torchvision torchaudio --default-index https://download.pytorch.org/whl/cu130

pyproject.toml

[project]
name = "morfem-dataset"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.12"
dependencies = [
    "datasets>=4.0.0",
    "duckdb>=1.3.2",
    "evaluate>=0.4.6",
    "ffmpeg>=1.4",
    "ipykernel>=6.30.1",
    "jupyter>=1.1.1",
    "loguru>=0.7.3",
    "notebook>=7.4.5",
    "ollama>=0.5.3",
    "pandas>=2.3.2",
    "peft>=0.18.0",
    "pydantic>=2.11.7",
    "python-dateutil>=2.9.0.post0",
    "python-dotenv>=1.1.1",
    "python-levenshtein>=0.27.1",
    "rich>=14.1.0",
    "scikit-learn>=1.7.2",
    "seqeval>=1.2.2",
    "termcolor>=3.1.0",
    "torch>=2.9.0",
    "transformers>=4.56.1",
]
