# ChatACT — Domain-Specific Accounting Q&A Assistant

**Undergraduate research project | National Chengchi University (NCCU) | 5-person team**

ChatACT is a prototype Chinese-language question-answering assistant designed to help small and medium-sized accounting firms respond to questions about **company registration regulations in Taiwan**. It explores whether domain-specific data preparation and parameter-efficient fine-tuning can improve the relevance of LLM-generated answers.

> **Repository status:** Research portfolio and project documentation. The training code, model weights, and full dataset are not currently published. The results below are from the team's project presentation, not a public production deployment.

## Project overview

- **Problem:** General-purpose chatbots may return broad answers that do not directly address Taiwan-specific company-registration questions.
- **Approach:** Prepare a domain-specific Chinese Q&A dataset, evaluate candidate language models, fine-tune them with **LoRA (Low-Rank Adaptation)**, and compare generated responses with reference answers.
- **Intended users:** Small and medium-sized accounting firms and their customers.

## Technical workflow

1. **Data collection and preparation** — Gather publicly accessible Q&A and regulatory information from Taiwanese government and accounting-related websites; normalize inconsistent scraped content and Q&A formats.
2. **Dataset augmentation** — Expand 286 original entries with 699 paraphrased or derived entries, producing **985 Q&A entries** in the team's reported dataset.
3. **Model experiments** — Experiment with **ChatGLM-6B** and **Chinese-LLaMA-Alpaca-2**, using LoRA-based fine-tuning and hyperparameter adjustments.
4. **Evaluation** — Compare automatic text-overlap metrics and human assessments; demonstrate a prototype Q&A interface.

## Reported results

| Metric / evaluation | Reported result | Scope |
| --- | ---: | --- |
| Dataset size | 985 Q&A entries | 286 original + 699 augmented |
| F1 score | 0.73 | Reported model-comparison result for Chinese-LLaMA-Alpaca-2; associated with text-overlap evaluation in the presentation |
| Precision | 0.58 | Same model-comparison table |
| BLEU-4 | 41.14 | Same model-comparison table |
| Human evaluation | 3 / 5 average | Inference-stage assessment using 33 questions and 10 accounting-domain professionals |

**Interpretation note:** These are results reported in the original student presentation. The automatic scores and the human-evaluation average come from different assessment sections and should not be interpreted as a single standardized benchmark. Slide 23 also reports **4.42 / 5** for Chinese-LLaMA-Alpaca-2 in a separate model-selection evaluation; that is **not** the same as the 3/5 inference-stage result.

## My contributions

As a member of the five-person team, I:

- Led **model selection and supervised fine-tuning**, including LoRA-based experiments with Chinese-language LLMs.
- Cleaned and standardized inconsistent web-scraped regulatory content and Q&A formatting to prepare domain-specific training data.
- Proposed the overall system architecture and helped connect the model workflow to the proposed accounting-service use case.

Other elements of the system and the reported results were developed and evaluated as a **team**.

## Research recognition

- Supported by an approved and completed **National Science and Technology Council (NSTC) undergraduate research project**.
- Selected as a finalist in the **28th National Collegiate Information Applications Innovation Contest**.

## Presentation and demo

- [Project presentation (PDF)](docs/ChatACT-presentation.pdf)
- [Recorded system demo](docs/ChatACT-demo.mp4)

## Limitations

This was an academic prototype focused on a narrow regulatory topic. Generated answers may be incorrect, incomplete, or outdated and should not be treated as professional accounting or legal advice. No claim is made that this system was deployed to paying customers.

## Publication note

The presentation, datasets, figures, and other team-generated materials should only be published with the necessary permissions. No credentials, private customer information, restricted training data, or model weights are included in this repository.

