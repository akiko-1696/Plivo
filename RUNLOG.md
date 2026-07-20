# RUNLOG

## Run 1 - Baseline

**Hypothesis**

Establish the baseline performance of the provided implementation.

**Changes**

None.

**Dev BPB**

Not recorded.

**Conclusion**

Used as the reference implementation before modifications.

---

## Run 2 - Optimizer Improvements

**Hypothesis**

Modern Transformer optimization techniques (AdamW, cosine learning rate scheduling and gradient clipping) should improve optimization and reduce evaluation BPB.

**Changes**

- Adam → AdamW
- Weight decay = 0.1
- Betas = (0.9, 0.95)
- CosineAnnealingLR scheduler
- Gradient clipping (max_norm = 1.0)

**Dev BPB**

2.3718

**Conclusion**

Training remained stable throughout all 2000 steps and produced the best evaluation metric. This checkpoint was selected for submission.

---

## Run 3 - Weight Tying + GPT-2 Initialization

**Hypothesis**

Weight tying and GPT-2 style initialization may improve generalization without increasing parameter count.

**Changes**

- Enabled tied input/output embeddings
- Initialization std changed from 0.05 to 0.02

**Dev BPB**

2.3718

**Conclusion**

No measurable improvement was observed under the fixed 2000-step training budget. The checkpoint from Run 2 was retained.
