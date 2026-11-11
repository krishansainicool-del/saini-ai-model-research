# EXP002 — Gemma 4 26B-A4B

**Priority 2 | Status: not started**

## Research question
Can an architecture-compatible parameter-efficient adaptation of this 26B-class mixture-of-experts model improve multilingual task accuracy without damaging instruction following or exceeding a bounded compute budget?

## Checkpoint and tooling gate
- Verify the exact model repository, revision, license, model architecture and tokenizer.
- Confirm the **actual supported** training path for the selected Gemma 4 variant (MoE adapters can require model-specific target modules/tooling).
- Validate low-memory inference and GPU placement **before** attempting an adapter fit.
- Record total model size, active parameters and memory used; do not treat active-parameter count as total model weight size.
- No model downloads, external service writes, training or paid credits until compatibility and hardware requirements are verified.

## Experiment sequence
1. Run [GPU preflight](../notebooks/00_gpu_preflight.ipynb) in a separate research notebook.
2. Confirm checkpoint licensing and training-library compatibility.
3. Produce identical held-out baseline tasks for Hindi, Punjabi, Haryanvi and English.
4. Measure the actual inference memory and throughput using the supported model loader.
5. Attempt a small, bounded adapter training run if GPU and training compatibility gates pass.
6. Compare baseline versus adapted performance and document failures/regressions.

## Required artifact checklist
- [ ] Exact source checkpoint/revision and license
- [ ] MoE adapter support verified
- [ ] Permissioned datasets and frozen hold-out split
- [ ] GPU preflight and baseline logs
- [ ] Adapter training result or blocked-reason report
- [ ] Held-out multilingual/coding/tool-use evaluation
- [ ] Reproducibility and publication-rights review

No weights have been downloaded or trained as part of writing this plan.
