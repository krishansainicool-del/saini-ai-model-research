# SAINI AI — Open Model Research

**Status: planning and baseline preparation.** This repository documents proposed work. It does not claim completed fine-tuning runs, benchmark improvements, awarded grants, or exclusive ownership of third-party foundation models.

SAINI AI is an independent developer-led research project in India studying **compute-efficient adaptation and reproducible evaluation of open-weight AI models**. The initial evaluation languages are Hindi, Punjabi, Haryanvi, and English. Research also covers coding, instruction following, structured outputs, and tool-use reliability.

## Research goals

- Establish trustworthy baselines before any fine-tuning.
- Measure whether LoRA/QLoRA adapters improve clearly defined multilingual tasks without causing regressions.
- Compare VRAM use, throughput, latency, training time, and cost across model sizes and quantization methods.
- Explore architecture-appropriate and license-compliant ways to evaluate larger mixture-of-experts checkpoints.
- Publish methods and aggregate findings where data rights and model licenses permit.

## Candidate model inventory

| Model | Planned role | Current status |
| --- | --- | --- |
| [Qwen3-14B](https://huggingface.co/Qwen/Qwen3-14B) | First multilingual QLoRA baseline | Not started |
| [Phi-4](https://huggingface.co/microsoft/phi-4) | Compact comparison model | Not started |
| [Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Larger multilingual/coding model | Feasibility pending |
| [Gemma 4 26B-A4B](https://huggingface.co/google/gemma-4-26B-A4B-it) | Mixture-of-experts adaptation | Feasibility pending |
| [Llama 3.3 70B](https://huggingface.co/meta-llama/Llama-3.3-70B-Instruct) | 70B-class experiments | License/hardware review pending |
| [DeepSeek V4.1 Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | Giant-model feasibility research | No training scheduled |
| [GLM-5.3](https://huggingface.co/zai-org/GLM-5.3) | Giant-model feasibility research | No training scheduled |
| [Qwen3.8 2.4T-A95B](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B) | Very-large-scale system study | No training scheduled |

The inventory is a **research wishlist**, not a promise that all models can be trained for free. For every checkpoint, confirm the exact repository revision, applicable license and availability before downloading or adapting. Open weights do not transfer ownership of the foundation model.

## Methodology at a glance

1. Freeze a dataset and evaluation split. Use legitimately sourced, permissioned data.
2. Record exact upstream model revision, license, tokenizer, prompts, hardware and seed.
3. Evaluate the unmodified model first.
4. Run one controlled parameter-efficient fine-tuning experiment.
5. Re-evaluate on the same held-out tasks; report gains, regressions and uncertainty.
6. Publish reproducible configurations, aggregate results and limitations; do not publish secrets or private data.

**Project documentation**
- [12-week research roadmap](RESEARCH_ROADMAP.md)
- [Evaluation protocol and report template](EVALUATION_PROTOCOL.md)
- [Compute, licensing and data safeguards](COMPUTE_AND_SAFETY.md)

## First experiment

The initial target is **Qwen3-14B QLoRA** on an available free 16GB-class GPU, subject to a small memory smoke test. If it fails to fit or complete within the available session/quota, lower sequence length or use an appropriately smaller licensed checkpoint for pipeline verification before spending money. No training job is claimed complete.

## Open research and collaboration

Planned outputs: benchmark definitions, evaluation scripts, experiment manifests, memory/cost measurements, and technical notes. Checkpoint or adapter publication depends on upstream licenses and rights to the training data.

SAINI AI's production services, customer data, credentials, Kaggle music-generation pipelines and private application code are **out of scope** for this public repository. Never publish API keys, environment files, customer information or private model artifacts.

Maintained independently in India. Research contact can be provided through GitHub issues.
