# Compute, licensing and data safeguards

## Compute stages
1. **Free smoke test:** Kaggle (subject to allocated GPU hours) or a permitted free notebook; make the smallest experiment run end-to-end.
2. **Credit-backed training:** use Modal or an awarded GPU grant only after checking remaining credits and the exact GPU quota.
3. **Larger-model feasibility:** validate memory, storage, distributed software and legal permissions before allocating multi-GPU infrastructure.
4. **Serving:** independently hosting a checkpoint still requires compute; storing weights does not mean free always-on inference.

No credit award or training access is guaranteed. Current free quota and GPU availability must be verified before any run. SAINI AI's music-generation GPU credits and running jobs must not be repurposed without separate approval.

## Model licenses
- Record the exact license and copyright/notice requirements for **each specific model revision**.
- Preserve upstream attribution, naming requirements and restrictions for redistribution and commercial deployment.
- Do not relicense third-party foundation weights as MIT/Apache unless their terms actually permit it.
- Adapter and merged-checkpoint release requires a separate license/data review.
- Prefer downloadable checkpoints with permissive licenses for independent deployments.

## Privacy and security
- Never commit provider secrets, personal data, private recordings, credentials, recovery phrases, Cloudflare tokens or production files.
- Use dummy fixtures for public coding/agent benchmarks.
- Keep research datasets and evaluation outputs separate from production logs.
- Disable paid jobs automatically at predeclared limits; record expected cost before launch.
- Provide a rollback procedure before any integration into SAINI AI services.

## Model-size reality check
A 13B-active or 95B-active mixture-of-experts model may still have hundreds of billions or trillions of **total** parameters. GPU requirements depend on total weights, precision, optimizer states, activation memory, communication overhead and training method. A small free GPU is not a reliable full fine-tuning solution for these checkpoints.

## Public status policy
Clearly label each result **planned**, **in progress**, **completed**, or **not reproducible**. Do not imply a grant application is an award. Do not claim that benchmarking or training has succeeded until logs and artifacts verify it.
