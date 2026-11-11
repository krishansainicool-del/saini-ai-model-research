# SAINI AI — 12-week research roadmap

**Status: proposed.** The schedule starts only after an environment and baseline dataset are ready. All milestones are contingent on hardware access and upstream model compatibility.

## Week 1–2: Reproducible baseline
- Confirm checkpoint names, exact revisions, licenses, usage restrictions and download sizes.
- Build a permissioned, versioned multilingual evaluation set with held-out items.
- Define a stable evaluation harness for task success, formatting compliance, latency and memory.
- Run a tiny smoke test without adapting a model; record reproducibility manifest.
- **Exit gate:** baseline results are saved with model revision, dataset version and hardware manifest.

## Week 3–4: First parameter-efficient experiment
- Start with a Qwen3-14B LoRA/QLoRA feasibility test on a free GPU when allocated.
- Use a controlled dataset and split; log hyperparameters, time, GPU peak VRAM and failures.
- Compare baseline and adapter under identical evaluation settings.
- **Exit gate:** a reproducible result, including regressions, or a documented limitation.

## Week 5–6: Compact comparison
- Compare Phi-4 14B and, if feasible, a 14B reasoning-oriented checkpoint.
- Evaluate Hindi/Punjabi/Haryanvi/English understanding and code/tool-use tasks.
- Include negative controls and held-out examples to detect overfitting.
- **Exit gate:** comparable tables with uncertainty and compute-cost analysis.

## Week 7–8: 26–27B feasibility
- Assess Qwen3.8-27B and Gemma 4 26B-A4B with model-specific architectures.
- Test tokenizer support and quantized inference first, then LoRA only if a supported recipe and sufficient VRAM are available.
- **Exit gate:** a repeatable memory and throughput profile, not a forced training run.

## Week 9–10: Large and mixture-of-experts models
- Review licensing, memory budgets, distributed training libraries and available compute for Llama 3.3 70B, DeepSeek V4.1 Flash, GLM-5.3 and Qwen3.8 2.4T.
- Attempt only short, bounded feasibility experiments if compatible compute and permissions are granted.
- Do not assume free notebooks can train hundreds-of-billions or trillion-parameter checkpoints.
- **Exit gate:** validated cost/feasibility report or documented reasons to defer.

## Week 11–12: Reproduction and publication
- Rerun the most promising supported experiment.
- Check multilingual regressions, held-out performance, safety of generated output and hardware-cost totals.
- Publish evaluation scripts, aggregate measurements, experiment cards, and limitations.
- Publish adapters only when model and data permissions allow.

## Decision gates
- **Go:** statistically credible improvement on held-out tasks plus reproducibility and acceptable costs.
- **Revise:** mixed outcomes, memory issues, or high error rates.
- **Stop:** no valid data rights, license noncompliance, unavailable hardware, unaffordable compute, or unacceptable quality regression.

## What is not promised
No grant approval, model ownership transfer, guaranteed performance uplift, giant-model training completion, or zero-cost 24/7 inference is implied by this roadmap.
