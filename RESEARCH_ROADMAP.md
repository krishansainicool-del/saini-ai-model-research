# SAINI AI — 12-week research roadmap

**Status: proposed; no model training or benchmark completion claimed.** Priorities are **Qwen3.8 27B first**, then **Gemma 4 26B-A4B**. All other models are explicitly deferred until the first two experiments have meaningful results or a documented infeasibility verdict.

## Week 1–2: Environment and license verification for both target models
- Confirm exact downloadable checkpoint paths, revisions, licenses and tokenizer/model architecture.
- Check compatibility with available LoRA/QLoRA training code, especially Gemma 4's mixture-of-experts architecture.
- Run the separate [GPU preflight notebook](notebooks/00_gpu_preflight.ipynb) on Kaggle to record GPU type, VRAM, CPU RAM, disk, Python/PyTorch/CUDA versions and free quota availability.
- Design a permissioned, versioned Hindi/Punjabi/Haryanvi/English dataset with held-out evaluation items.
- **Exit gate:** a model-specific feasibility decision and a dataset manifest, without downloading huge weights blindly.

## Week 3–5: Experiment 001 — Qwen3.8 27B
- Follow [EXP001](experiments/EXP001_QWEN38_27B.md).
- Obtain baseline results and memory/throughput readings with a supported quantized inference configuration.
- Only after baseline success, attempt capped LoRA/QLoRA on a supported compatible GPU configuration.
- Record model revision, hyperparameters, compute time, peak VRAM, failures, baseline and adapter scores.
- **Exit gate:** reproducible evaluated adapter **or** an honest blocked-by-compute/compatibility result.

## Week 6–8: Experiment 002 — Gemma 4 26B-A4B
- Follow [EXP002](experiments/EXP002_GEMMA4_26B.md).
- Validate model access, tokenizer/architecture support, low-memory inference and an MoE-compatible adapter recipe.
- Run a bounded training experiment only if compatibility, license/data rights and hardware gates pass.
- Compare against the same evaluation protocol while documenting architecture differences.
- **Exit gate:** reproducible evaluated adapter **or** a documented reason to defer.

## Week 9–10: Compare and reproduce
- Compare both models using identical held-out datasets, task rubrics and known hardware configurations.
- Report language-wise task correctness, code tests, structured output accuracy, latency, throughput, VRAM and compute cost.
- Rerun the best feasible experiment and investigate regressions.

## Week 11–12: Publish technical evidence
- Release reproducible benchmark definitions and scripts, experiments and failure logs as appropriate.
- Publish technical findings with exact versions and limitations.
- Release compatible adapters only if upstream licensing and dataset rights permit.
- **Only then** revisit Qwen3-14B, Phi-4, Llama 3.3 70B, DeepSeek V4.1, GLM-5.3 and Qwen3.8 Max.

## Compute and stop rules
- Use free research GPU allocations first; their availability, memory and session limits are not guaranteed.
- Do not reuse the SAINI AI Songs training environment or ACE-Step XL Modal credits without separate approval.
- Stop if licenses, data rights, hardware or dependencies do not meet the experiment requirements.
- Do not claim giant-model full fine-tuning or zero-cost continuous hosting.

No grant approval, training success, or model ownership transfer is implied.
