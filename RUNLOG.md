# Run Log

## Baseline
- Original starter code.
- Used as reference.

---

## Experiment 1 (Submitted)

### Hypothesis
The baseline optimizer could be improved using modern Transformer training practices.

### Changes
- Replaced Adam with AdamW.
- Added cosine learning rate scheduler.
- Added gradient clipping (max_norm = 1.0).
- Weight decay = 0.1.
- Betas = (0.9, 0.95).

### Result
- Training completed successfully for 2000 steps.
- Final training loss: ~1.73.
- Dev BPB: **2.3718**.

### Conclusion
Training remained stable and produced the best checkpoint selected for submission.

---

## Experiment 2

### Hypothesis
Weight tying and GPT-2 style initialization might improve generalization.

### Changes
- Enabled weight tying.
- Changed initialization standard deviation from 0.05 to 0.02.

### Result
Training completed successfully, but the evaluation BPB remained **2.3718**, showing no measurable improvement under the fixed training budget.

### Conclusion
The previous checkpoint was retained for submission.
