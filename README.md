## Mitigating Predictive Bias in Formula 1 Pit Stop Data Using Disaggregated ML Models

This repository contains the code for a research-focused machine learning project that investigates predictive bias in Formula 1 pit stop data and evaluates disaggregated machine learning models as a fairness intervention.

The project examines whether historical race data disproportionately favours top-tier Formula 1 constructor teams in predictive models, and whether training specialised models for different team tiers can reduce this bias.

## Project Context

This work was developed during a six-week F1 Flux Research Programme delivered by **[Femetronics](https://www.femetronics.com/)**, which provided structured mentoring in artificial intelligence, machine learning fundamentals, fairness-aware modelling, and academic research practices.

## Collaboration

This project was completed as a collaborative research effort involving five participants under a shared research framework. While the research question, dataset, and evaluation strategy were defined collectively, the technical implementations were carried out independently across projects.

Two pairs of participants developed their modelling pipelines collaboratively, while I completed an independent implementation **(Project C)**. This repository contains my individual codebase, including data preprocessing, model training, fairness evaluation, and result interpretation, along with the final integrated research report produced from the collaborative work.

In addition to the technical implementation, the final research report was written collaboratively. Draft sections were contributed by different participants, after which I led the integration and final assembly of the report. This included coordinating progress check-ins, creating a shared template to ensure consistency, consolidating contributions, formatting the document, and managing word-count and structural requirements to meet the submission deadline.

## Research Objective

The central research question explored in this project is:

> *Can disaggregating Formula 1 pit stop data by constructor tier and training specialised machine learning models reduce predictive bias compared to a single unified model?*

## Dataset Overview

- **Domain:** Formula 1 pit stop and stint performance data  
- **Time period:** 2018–2024  
- **Target variable:** Lap Time Variation (seconds)  
- **Source:** Kaggle – [F1 Stint Data with Aggression Scores](https://www.kaggle.com/datasets/akashrane2609/f1-stint-data-with-aggression-scores)

### Key features used:
- Stint Length  
- Air Temperature  
- Tyre Compound  
- Constructor (used only for fairness analysis, not as a model input)

Constructor teams are grouped into top-tier and other-tier categories to evaluate predictive parity.

## Methodology

The project follows a fairness-aware machine learning workflow:

1. Data loading and cleaning  
2. Training a unified Decision Tree Regressor to establish baseline performance  
3. Measuring predictive bias using Mean Absolute Error (MAE) across team tiers  
4. Applying a fairness intervention by training disaggregated, specialised models  
5. Comparing MAE disparities before and after mitigation  

Constructor tier is treated as a protected attribute and is excluded from the specialised model inputs to prevent label leakage and preserve generalisability.

## Conclusion

This project shows that predictive bias in Formula 1 pit stop data can stem from structural inequalities in historical datasets. By training disaggregated models for different constructor tiers, the gap in MAE between teams was significantly reduced, improving predictive parity, even though overall model performance did not improve. This helps illustrate why fairness-aware evaluation matters in real-world machine learning.
