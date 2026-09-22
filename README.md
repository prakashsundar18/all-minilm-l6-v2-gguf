# all-MiniLM-L6-v2 (GGUF, Q4_K_M)

A quantized GGUF build of [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2), a compact sentence-embedding model. Sourced from [second-state/All-MiniLM-L6-v2-Embedding-GGUF](https://huggingface.co/second-state/All-MiniLM-L6-v2-Embedding-GGUF) on Hugging Face.

## Contents

- `all-minilm-l6-v2-q4_k_m.zip` — zipped model file, containing:
  - `all-MiniLM-L6-v2-Q4_K_M.gguf` (~20 MB, Q4_K_M quantization)

Small enough to be tracked as a regular git file (no Git LFS needed).

## Download

```bash
git clone https://github.com/prakash-emb/all-minilm-l6-v2-gguf.git
cd all-minilm-l6-v2-gguf
unzip all-minilm-l6-v2-q4_k_m.zip
```

Or download the zip directly from the repo's file view on GitHub and unzip it.

## Usage

This is an **embedding model** (produces vectors, not text completions), so it needs an embedding-capable runtime.

### llama.cpp

```bash
git clone https://github.com/ggerganov/llama.cpp
cd llama.cpp
cmake -B build
cmake --build build --config Release

./build/bin/llama-embedding -m /path/to/all-MiniLM-L6-v2-Q4_K_M.gguf -p "Your text here"
```

### Ollama

```
FROM /path/to/all-MiniLM-L6-v2-Q4_K_M.gguf
```

```bash
ollama create all-minilm-l6-v2 -f Modelfile
ollama run all-minilm-l6-v2 --embed
```

Or use it with any other GGUF-compatible embedding runtime (LM Studio, text-embeddings-inference, koboldcpp, etc.) by pointing it at the extracted `.gguf` file.

## License

Apache 2.0, per the original [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) model.
