---
base_model: unsloth/gpt-oss-20b-unsloth-bnb-4bit
tags:
- text-generation-inference
- transformers
- unsloth
- gpt_oss
- trl
license: apache-2.0
language:
- en
---


# Bio-GPT-OSS-20B

A specialized biomedical question-answering model fine-tuned from [gpt-oss-20B](https://huggingface.co/gpt-oss-20B) on scholarly Q&A extraction tasks from biomedical research papers.

# Bio-GPT-OSS-20B/ Bio-GPT-OSS-20B pubmed 


 <img src="OpenAI Bio-OSS-20B Logo Design.png" height="600" width="940" >



## Model Details

- **Base Model**: gpt-oss-20B
- **Fine-tuned on**: Biomedical scholarly Q&A dataset
- **Task**: Question answering from scientific papers with step-by-step reasoning
- **Parameters**: ~20B
- **Language**: English



## Training Data

The model was trained on ~ 1000 conversation pairs extracted from biomedical research papers, featuring:

- **Dataset**: [Pubmed-Bio-Thinking-1000](https://huggingface.co/datasets/MehdiHosseiniMoghadam/Pubmed-Bio-Thinking-1000)
- **Data**: 100000 & 1000000 version of the Dataset is avalible, contact for access
- **System**: Scholarly Q&A extraction agent instructions
- **User**: Complex biomedical questions about research findings
- **Analysis**: Detailed step-by-step reasoning and evidence extraction
- **Final**: Concise, precise answers with citations

### Data Structure

```json
{
  "paper_id": "PMC8026465",
  "reasoning_language": "English",
  "developer": "You are a scholarly Q & A extraction agent. Only use the provided paper. Be concise and precise.",
  "user": "According to the comparative analysis by Wu et al., how do the kidney organoid differentiation protocols compare?",
  "analysis": "Steps:\n1) Locate the section \"3D kidney organoids\"...\n2) Find Wu et al. comparative study...",
  "final": "According to Wu et al., both Morizane and Takasato protocols generated immature tissue, expressing ~20% of adult transcription factors.",
  "messages": [
    {"role": "system", "content": "...", "thinking": null},
    {"role": "user", "content": "...", "thinking": null},
    {"role": "assistant", "content": "...", "thinking": "Steps:\n1) Locate..."}
  ]
}
```



### Sample Conversations

**Question**: Kidney organoid protocol comparison
**Analysis**: Multi-step evidence extraction from specific paper sections
**Answer**: Quantitative comparison with statistical details (both protocols ~20% maturity)

**Question**: Cognitive test predictive ability differences  
**Analysis**: Statistical result extraction and comparison across test conditions
**Answer**: 1-week test superior predictive power (p=.003 vs p=.11)

## Intended Use

- Biomedical research question answering
- Scientific paper analysis and extraction
- Evidence-based reasoning in life sciences
- Academic research assistance

## Limitations

- Domain-specific to biomedical/life sciences literature
- Requires access to source papers for optimal performance
- May not generalize well outside scholarly contexts

## Citation

```bibtex
@model{bio-gpt-oss-20b,
  title={Bio-GPT-OSS-20B: Biomedical Question Answering with Reasoning},
  author={Your Name},
  year={2024},
  base_model={gpt-oss-20B}
}
```



This gpt_oss model was trained 2x faster with [Unsloth](https://github.com/unslothai/unsloth) and Huggingface's TRL library.

[<img src="https://raw.githubusercontent.com/unslothai/unsloth/main/images/unsloth%20made%20with%20love.png" width="200"/>](https://github.com/unslothai/unsloth)
