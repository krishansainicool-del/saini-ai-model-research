# SAINI AI — Open Model Research

**Status: planning and GPU preflight preparation.** No training job, evaluated checkpoint, awarded compute grant, or benchmark improvement is claimed in this repository.

SAINI AI is an independent developer-led research project in India investigating **compute-efficient adaptation and reproducible evaluation of open-weight AI models**, initially in Hindi, Punjabi, Haryanvi, and English. Additional targets include coding, instruction following, structured outputs and tool-use reliability.

## Current priority: two 26–27B-class models

**We are starting with these two models, in this order:**

| Order | Candidate checkpoint | Research objective | Status |
| --- | --- | --- | --- |
| **1** | [Qwen3.8 27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Multilingual instruction-following and coding; quantized baseline, then LoRA/QLoRA feasibility | **Preflight planned; not trained** |
| **2** | [Gemma 4 26B-A4B](https://huggingface.co/google/gemma-4-26B-A4B-it) | Multilingual evaluation and mixture-of-experts adaptation using architecture-compatible tooling | **Preflight planned; not trained** |

Model links reflect candidate identifiers, **not verified pinned revisions**. Confirm model identity, access, exact license and supported fine-tuning recipe before any download or training. These are two independent training tracks; the second will not consume compute until its own gate passes.

**Free-compute-first rule:** Test GPU memory, disk, framework support, checkpoint accessibility and baseline feasibility on a separate Kaggle research notebook before allocating paid GPUs or Modal credits. Kaggle T4 devices do not automatically pool their VRAM; fitting 26–27B adapters is **not assured**. Do not make unbounded downloads. Dedicated larger-memory GPU experiments require explicit approval and available credit.

- [GPU preflight notebook](notebooks/00_gpu_preflight.ipynb) — **does not download a model or start training**
- [Experiment 001: Qwen3.8 27B](experiments/EXP001_QWEN38_27B.md)
- [Experiment 002: Gemma 4 26B](experiments/EXP002_GEMMA4_26B.md)
- [Updated 12-week roadmap](RESEARCH_ROADMAP.md)
- [Evaluation protocol](EVALUATION_PROTOCOL.md)
- [Compute, licensing and safety safeguards](COMPUTE_AND_SAFETY.md)

## Other candidate models — deferred until the first two are evaluated

| Model | Current status |
| --- | --- |
| [Qwen3-14B](https://huggingface.co/Qwen/Qwen3-14B) | Deferred |
| [Phi-4](https://huggingface.co/microsoft/phi-4) | Deferred |
| [Llama 3.3 70B](https://huggingface.co/meta-llama/Llama-3.3-70B-Instruct) | Deferred; license/hardware review required |
| [DeepSeek V4.1 Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | Deferred; distributed-compute research |
| [GLM-5.3](https://huggingface.co/zai-org/GLM-5.3) | Deferred; distributed-compute research |
| [Qwen3.8 Max](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B) | Deferred; giant-model feasibility research |

This inventory is a research plan, **not** a claim that all checkpoints can be trained for free.

## Reproducible research approach

1. Verify the upstream model, revision, license, tokenizer and training-tool compatibility.
2. Freeze a permissioned training/development/held-out evaluation dataset.
3. Measure available memory/disk and evaluate the **unmodified checkpoint** first.
4. Attempt a resource-capped adapter training run **only after a feasible hardware plan exists**.
5. Re-evaluate with the same held-out tasks; publish improvements **and regressions**, hardware use and limitations.
6. Preserve upstream notices; publish adapters only where underlying rights permit.

Planned public outputs are experimental configurations, benchmark methodology, aggregate results, hardware/cost measurements, and technical notes. This repository does not contain production source, customer data, secrets or private application code. SAINI AI Songs Kaggle jobs and Modal ACE-Step XL credits remain out of scope.

For research discussions, use the GitHub Issues tab.
