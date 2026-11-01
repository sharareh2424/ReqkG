ReqKG: Evidence-Grounded Requirement Refinement

An Empirical Study of Ambiguity Detection, Evidence-Grounded Refinement, and Guarded Release in Software Requirements Engineering

⸻

1. Overview

ReqKG is an evidence-grounded framework for analyzing and refining ambiguous software requirements while preserving their original intent.

The framework investigates how requirement refinement can be performed without introducing unsupported information, changing stakeholder intent, or producing semantically unsafe modifications.

The proposed approach combines requirement screening, structured knowledge representation, evidence-based refinement, and policy-based output validation.

This repository contains the experimental implementation, evaluation procedures, reproducibility documentation, and supporting materials associated with the ReqKG research study.

2. Research Objectives

The study addresses the following research objectives:

* Identify ambiguity and potential defects in natural-language software requirements.
* Investigate evidence-grounded requirement refinement.
* Examine the contribution of structured knowledge representation to refinement quality.
* Evaluate whether a policy-based Guard can prevent unsupported or unsafe modifications.
* Measure semantic intent preservation through independent human assessment.
* Compare the proposed approach with classical machine-learning and transformer-based baselines.

3. Proposed Framework

The ReqKG framework consists of the following conceptual components:

3.1 Requirement Screening

The screening stage identifies potentially ambiguous or problematic requirements and supports the selection of requirements for further analysis.

3.2 Knowledge Graph Representation

The knowledge representation component organizes relevant entities, relationships, and available evidence to support traceable requirement refinement.

3.3 Evidence-Grounded Refinement

The refinement component generates candidate modifications using the available requirement context and supporting evidence.

3.4 Guarded Release

The Guard evaluates candidate modifications against predefined acceptance conditions before release.

A candidate that does not satisfy the required conditions is rejected or withheld rather than automatically accepted.

4. Datasets

The study uses multiple datasets for different experimental purposes.

Dataset	Research purpose
Fault-Prone SRS	Requirement screening and classification experiments
ORCHID	Requirement refinement and evidence-grounding evaluation
QuRE	Supporting industrial requirements evaluation

The datasets serve different experimental roles and should not be treated as interchangeable.

Dataset Reproducibility

For each dataset, the experimental workflow should document:

* Original source and publication.
* Dataset version.
* Access or download procedure.
* Number of instances used.
* Feature and label definitions.
* Preprocessing operations.
* Training, development, and test partitions.
* Random seeds.
* Dataset licensing and redistribution restrictions.

The original datasets are not redistributed through this repository unless their respective licenses explicitly permit redistribution.

Users should obtain restricted or externally hosted datasets from their original sources.

5. Human Evaluation

Human evaluation is an important component of the study.

Two independent assessors, identified as AR and MK, participated in the assessment procedure.

The evaluation concerns:

* Ambiguity resolution.
* Unsupported or unsafe modifications.
* Preservation of original intent.

The original human-evaluation implementation is retained in the research notebook.

The evaluation workflow includes:

1. Preparation of assessment items.
2. Independent assessor responses.
3. Collection of assessment records.
4. Agreement analysis.
5. Cohen’s Kappa calculation.
6. Reporting of disagreements and evaluation limitations.

The reported agreement statistics must be interpreted according to the original assessment protocol.

No additional adjudication or recalibration should be assumed unless documented in the corresponding experimental records.

6. Experimental Evaluation

The experimental implementation includes:

* Classical machine-learning baselines.
* Transformer-based classification models.
* Requirement refinement experiments.
* Knowledge representation comparisons.
* Guard evaluation.
* Human assessment.
* Statistical and sensitivity analyses.

The factorial experimental design examines the contribution of the following components:

* P: Parsing.
* K: Knowledge Graph.
* G: Guard.

The implementation and reported experimental results should be interpreted together with the corresponding tables and methodological descriptions in the research manuscript.

Incomplete or exploratory executions must not be presented as completed experimental results.

7. Repository Structure

ReqKG/
│
├── README.md
│
├── notebooks/
│   └── ReqKG.ipynb
│
├── docs/
│   ├── DATASETS.md
│   ├── HUMAN_EVALUATION.md
│   └── REPRODUCIBILITY.md
│
├── data/
│   └── README.md
│
├── results/
│   └── README.md
│
└── requirements-notebook.txt

8. Installation

The experiments are implemented in Python and can be executed using Jupyter Notebook or Google Colab.

Install the required dependencies:

pip install -r requirements-notebook.txt

Some experiments may require additional computational resources, depending on the model and dataset configuration.

GPU acceleration is recommended for transformer-based experiments.

9. Running the Experiments

Open the main research notebook:

notebooks/ReqKG.ipynb

Recommended execution procedure:

1. Configure the runtime environment.
2. Obtain the required datasets.
3. Verify dataset paths and versions.
4. Set the random seeds.
5. Execute the preprocessing procedures.
6. Run the relevant experimental sections.
7. Execute the evaluation procedures.
8. Export the resulting tables and metrics.

The notebook documents the experimental workflow and its dependencies.

Previously reported results should be distinguished from newly generated results.

10. Reproducibility

To support reproducibility, the following information should be preserved for each experimental run:

* Python version.
* Package versions.
* Operating system.
* Hardware configuration.
* Model identifiers and versions.
* Dataset versions and checksums.
* Random seeds.
* Data partition identifiers.
* Evaluation configurations.
* Per-instance predictions.
* Aggregated evaluation metrics.

The documentation files provide additional information about dataset access, human evaluation, and experimental reproduction.

11. Data and Code Availability

The source code and research documentation are provided through this repository.

Dataset availability is subject to the original dataset providers’ access conditions and licensing restrictions.

Human assessment records should only be released in anonymized form and where permitted by the relevant data-protection and research-ethics requirements.

A permanent archival DOI should be added after the corresponding research materials have been deposited and publicly released.

12. Research Limitations

The study includes diagnostic findings concerning the limitations of evidence-grounded requirement refinement.

Important limitations include:

* Limited semantic coverage of the Guard.
* Conservative rejection of candidate modifications.
* Imperfect agreement between human assessors.
* Dataset-specific evaluation constraints.
* Incomplete statistical analyses for some model comparisons.
* Limited generalizability beyond the evaluated datasets.

These limitations are explicitly considered when interpreting the experimental findings.

13. Citation

If you use this implementation in academic research, please cite the associated research article.

Citation information will be added after the manuscript publication or assignment of a permanent archival DOI.

14. Contact

For questions concerning the implementation, experimental methodology, or research materials, please contact the corresponding author.

⸻

Project: ReqKG
Research Area: Requirements Engineering
Implementation Language: Python
Primary Environment: Jupyter Notebook / Google Colab
Repository: https://github.com/sharareh2424/ReqkG
