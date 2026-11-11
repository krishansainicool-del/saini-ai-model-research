# Evaluation protocol and experiment log

**No benchmark results have been recorded in this repository yet.**

## Scope
Initial languages: Hindi, Punjabi, Haryanvi and English. Task families:
- **Instruction following:** fulfill explicit constraints, avoid omitted steps and unsupported claims.
- **Multilingual comprehension:** answer questions grounded in permissioned source passages in the specified language.
- **Coding:** evaluate on reproducible tests; pass/fail and runtime, not subjective fluency alone.
- **Tool/JSON reliability:** valid schema, correct tool selection and argument accuracy using sandboxed fixtures.
- **Safety and regressions:** compare refusal behavior on disallowed requests and harmless-task helpfulness.

## Dataset controls
- Obtain licensed or author-created examples; document provenance and allowed uses.
- Freeze independent train/dev/test partitions. Do not tune on the held-out test set.
- Track duplicates, translation leakage and near-duplicates across splits.
- Document language variety and human-review protocol for Haryanvi and Punjabi.
- Exclude sensitive personal data, copyrighted corpora without permission, private conversations and credentials.

## Controlled experiment
Compare baseline and adapted model on the **same held-out set** using:
- Same prompt template, decoding settings, context length, test questions and judging rubric.
- Fixed model revision, tokenizer, dataset version, random seed and dependency versions.
- Exact LoRA/QLoRA parameters, optimizer, precision, quantization and training steps.
- GPU type/count, device memory, peak allocated VRAM, elapsed time, token throughput and estimated spend.
- Structured logs of errors, timeouts, OOMs and failed trials.

## Metrics
| Area | Primary metric | Additional check |
| --- | --- | --- |
| Instruction following | Valid task completions / total | Constraint-by-constraint breakdown |
| Multilingual accuracy | Human-verified exact/task score | By-language error categories |
| Code | Unit tests passed | Runtime and failure classes |
| Structured outputs | Schema-valid responses | Correct semantic arguments |
| Inference | Tokens per second, latency p50/p95 | Peak VRAM and quantization |
| Training | Training tokens/hour, total elapsed | GPU-hours and monetary cost |
| Regression | Paired pass-rate delta | Per-task and per-language failures |

Report sample counts, confidence intervals where possible, and all quality regressions. Do not label an ASR or automated scoring result as human verification.

## Minimum experiment record
| Field | Required value |
| --- | --- |
| Experiment ID / date | Not started |
| Upstream checkpoint revision and license | To be recorded |
| Dataset hash and train/dev/test sizes | To be recorded |
| Trainable parameters / adapter recipe | To be recorded |
| Hardware, VRAM peak and GPU hours | To be recorded |
| Baseline scores | To be recorded |
| Adapted-model scores | To be recorded |
| Regressions and limitations | To be recorded |
| Reproduction instructions | To be recorded |

## Publication rule
Publish raw evaluation items only if redistribution is authorized. Otherwise release aggregate scores, data-construction methodology and code that runs on substitute publicly licensed datasets. Never present planned work as completed.
