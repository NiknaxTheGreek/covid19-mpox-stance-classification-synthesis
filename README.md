# From COVID-19 Vaccine Hesitancy to Mpox

## A Comparative Study of Stance Labelling and Machine-Learning Classification

This repository contains a scientific synthesis of two published collaborative studies examining human labelling, sentiment/stance classification, and cross-crisis transformer adaptation across COVID-19 vaccine discourse and the 2022 Mpox outbreak.

**Author:** Nicholas Perikli  
**Report type:** Scientific synthesis of published collaborative research

## Report

The final report is provided as:

`From_COVID19_Vaccine_Hesitancy_to_Mpox_Comparative_Synthesis_FINAL.pdf`

The report integrates the two studies into one comparative methodological narrative rather than treating them as independent case studies. It focuses on the progression from manually labelled COVID-19 vaccine-related Twitter data to transfer and domain-specific fine-tuning for Mpox stance classification.

## Scientific questions

The synthesis examines two related questions:

1. How reliably can context-sensitive human labelling support stance and sentiment classification in linguistically complex public-health social-media data?
2. To what extent do transformer models adapted to COVID-19 health discourse retain useful predictive information when transferred to Mpox, and how much additional improvement is obtained from Mpox-specific fine-tuning?

## Datasets

The COVID-19 study used a manually labelled corpus of **30,000 South African vaccine-related tweets**, with positive, neutral and negative labels. The Mpox study used **20,604 manually labelled tweets** collected during the 2022 outbreak and retained the same three-class methodological lineage.

The corpora are methodologically related but are not treated as matched datasets: they differ in geographic scope, collection period, search criteria, public-health context and class distribution.

## Labelling methodology

Manual annotation is treated as a central methodological component rather than a preprocessing detail. The COVID-19 study used 11 annotators and an iterative consensus procedure. Mean Cohen's kappa increased from **0.67 to 0.85** after repeated review and refinement of the decision rules.

The annotation framework explicitly considered contextual features such as slang, sarcasm, punctuation, emojis and tone. VADER and TextBlob were later evaluated against human labels to quantify the limitations of automated polarity-based labelling.

## Modelling

The COVID-19 study compared:

- Support Vector Machine (SVM)
- LSTM
- Bidirectional LSTM
- BERT-base-cased
- RoBERTa-base

Hyperparameter optimisation used Bayesian optimisation through Weights & Biases with model-specific search spaces.

The Mpox study evaluated four transformer models before and after Mpox-specific fine-tuning:

- NLP-Town BERT
- Cardiff-NLP RoBERTa
- COVID-19 BERT
- COVID-19 RoBERTa

## Key published results

For COVID-19 three-class classification, the strongest overall F1-scores were **60% for BERT** and **61% for RoBERTa**. Removing the neutral class increased both transformer models to approximately **80% F1**, showing the substantial difficulty associated with neutral and subtly hesitant examples.

For Mpox, COVID-19 BERT and COVID-19 RoBERTa each achieved **45% F1 and 47% accuracy** before Mpox-specific fine-tuning, outperforming the generic pretrained alternatives. After fine-tuning on manually labelled Mpox data, performance increased to **68% F1 for BERT** and **69% F1 for RoBERTa**.

VADER achieved **47% F1 / 50% accuracy** and TextBlob **37% F1 / 40% accuracy** against the manually assigned Mpox stance labels, with particularly weak positive-class recall.

## Interpretation

The combined results support a layered view of cross-crisis adaptation. Prior training on related health discourse provides a useful starting representation, but it does not remove the need for new domain-specific supervision. Human-labelled data and transferable transformer representations therefore operate as complementary components of an adaptable public-health NLP framework.

## Scope and reproducibility

This repository is a **synthesis of published results**, not a new modelling experiment. No new model training, re-analysis or unreported performance values are introduced in the report. Figures and comparative tables are reconstructed only from values reported in the source publications.

## Core publications

1. N. Perikli et al., **“Detecting the Presence of COVID-19 Vaccination Hesitancy From South African Twitter Data Using Machine Learning,”** *IEEE Transactions on Computational Social Systems*, 2025. DOI: **10.1109/TCSS.2025.3608636**.

2. N. Perikli et al., **“Evaluating automatic annotation of lexicon-based models for stance detection of M-pox tweets from May 1st to Sep 5th, 2022,”** *PLOS Digital Health*, 3(7), e0000545, 2024. DOI: **10.1371/journal.pdig.0000545**.

The report bibliography additionally backtracks methodological and background claims to the relevant original literature rather than relying only on the two co-authored papers as secondary citations.

## Related research

The Discussion briefly connects the methodological skills developed in these public-health NLP studies to later MSc research on ATLAS TileCal detector-control alarms and predictive maintenance. This is presented as a methodological bridge rather than as a third empirical case study.

## Repository status

The PDF in this repository is the final readability-adjusted **12-page** version of the synthesis report.