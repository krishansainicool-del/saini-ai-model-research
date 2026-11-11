# EXP001 — Qwen3.8 27B

**Priority 1 | Status: not started**

## Research question
Can a compute-efficient, parameter-efficient adapter improve Hindi, Punjabi, Haryanvi and English instruction following, coding and structured outputs on held-out evaluations without unacceptable regressions?

## Checkpoint gate
- Confirm the exact source checkpoint and revision, original license, tokenizer and access conditions.
- Confirm compatibility with current quantization, attention and LoRA training libraries; record working versions.
- Check GPU memory, available host RAM, disk and runtime quota before downloading weights.
- Treat two 16GB T4 GPUs as **two separate memory spaces**, not a free 32GB pooled GPU.
- Do not auto-launch paid GPU jobs or consume Modal credits reserved for music production.

## Experiment sequence
1. Run [GPU preflight](../notebooks/00_gpu_preflight.ipynb) without downloads or training.
2. Record hardware and validated checkpoint revision in an experiment manifest.
3. Establish a small baseline inference benchmark in the four languages.
4. Verify a compatible, capped QLoRA/LoRA recipe; if available compute is insufficient, mark BLOCKED and document required VRAM instead of downscaling to an unrelated checkpoint without approval.
5. If the gate passes, run bounded adapter training on permissioned data, checkpoint outputs to private storage and log costs.
6. Evaluate on a held-out set; report language-wise scores, code unit tests, JSON validity, latency and VRAM, including regressions.

## Required artifact checklist
- [ ] Exact source checkpoint/revision and verified license
- [ ] Training and evaluation dataset provenance, hashes and splits
- [ ] GPU preflight log and tool versions
- [ ] Baseline quality/latency/VRAM report
- [ ] Adapter training manifest or blocked-reason report
- [ ] Post-adaptation evaluation (if trained)
- [ ] Reproducibility notes and publication-rights review

No weights have been downloaded or trained as part of writing this plan.
