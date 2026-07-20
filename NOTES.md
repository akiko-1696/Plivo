# Notes

## Approach

I first understood the provided GPT implementation and training pipeline before making incremental changes.

The focus was on improving optimization rather than making large architectural changes.

The primary modifications were:

- AdamW optimizer
- Cosine learning rate scheduling
- Gradient clipping

I also experimented with:

- Weight tying
- GPT-2 style parameter initialization

These latter changes did not improve the development BPB within the fixed 2000-step training budget.

## Future Work

With more time, I would investigate:

- Better tokenizer (especially for mixed English/Hindi text)
- Using more of the 2M parameter budget
- Longer context length
- Architecture search (depth vs width)
- Learning rate warmup
