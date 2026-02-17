Task 2 – Vision-Language Report Generation
Objective

Generate medical-style radiology reports from chest X-ray images using a pre-trained visual language model.

Model Selection

Model used: BLIP-2 (Salesforce/blip2-flan-t5-xl)

Justification:

Open-source

Compatible with Colab GPU

Supports image-conditioned text generation

Prompting Strategy

Several prompts were tested:

Direct descriptive prompts

Structured radiologist framing

Question–Answer format

The Q&A format produced more stable outputs.

Observations

Outputs frequently repeated the same pathological phrase.

Reports were identical across multiple images.

The model hallucinated pleural effusion even for normal images.

Low image resolution (28×28) likely limited feature extraction.

Qualitative Comparison

Across:

Correct pneumonia cases

Correct normal cases

False positives

False negatives

The VLM produced nearly identical outputs, suggesting limited image sensitivity.

Strengths & Limitations

Strengths:

Successfully integrated multimodal model

Demonstrated prompt experimentation

Limitations:

Domain mismatch (natural image pretraining)

Hallucination behavior

Repetitive outputs

Low dataset resolution

Conclusion

The VLM integration demonstrates feasibility but highlights limitations of generic multimodal models in medical imaging contexts.
