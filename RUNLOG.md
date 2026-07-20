# RUNLOG

## Run 1 - Optimizer Improvements

### Hypothesis
The baseline optimizer can be improved by adopting training practices commonly used for transformer models. Replacing Adam with AdamW, adding cosine learning rate scheduling, and applying gradient clipping should improve optimization stability and produce a lower evaluation BPB.

### Changes
- Replaced Adam with AdamW.
- Added weight decay = 0.1.
- Used betas = (0.9, 0.95).
- Added CosineAnnealingLR scheduler.
- Added gradient clipping (max_norm = 1.0).

### Results
- Training steps: 2000
- Final training loss: ~1.7315
- Development BPB: **2.3718**

### Conclusion
Training remained stable throughout the run and this configuration produced the best measured evaluation metric. This checkpoint was selected as the final submission.

---

## Run 2 - Weight Tying and GPT-2 Style Initialization

### Hypothesis
Weight tying and a smaller GPT-2 style initialization standard deviation may improve generalization without increasing the parameter budget.

### Changes
- Enabled tied input/output embeddings (`tie_weights=True`).
- Changed initialization standard deviation from 0.05 to 0.02.

### Results
- Training steps: 2000
- Development BPB: **2.3718**

### Conclusion
No measurable improvement over Run 1 was observed under the fixed training budget. The checkpoint from Run 1 was retained as the final submission.
