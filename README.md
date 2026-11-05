ReqKG Guard

This repository accompanies the study Evidence Authority in Automated Requirements Repair.

The research examines whether a proposed revision to a software requirement is justified by evidence approved for the relevant project and version. ReqKG Guard records the provenance of supporting assertions and checks a generated rewrite before releasing it.

For example, changing “the system should respond quickly” to “the system shall respond within two seconds” introduces a measurable obligation. Accepting this change requires an applicable, approved source that establishes the two-second limit.

Project repository
https://github.com/sharareh2424/ReqkG

Datasets

The study uses three datasets for different evaluation tasks.

SRS

The Fault-prone SRS dataset supports training and evaluating sentence-level ambiguity screening models. It provides requirement texts and the labels used in the screening study.

Dataset URL
https://www.kaggle.com/datasets/corpus4panwo/fault-prone-srs-dataset

ORCHID

The ORCHID benchmark supports the requirement-repair experiments. It provides ambiguous programming requirements and reference descriptions for evaluating candidate rewrites, evidence representations, and Guard release policies.

Dataset URL
https://huggingface.co/datasets/SII-YDD/Orchid

QuRE

The QuRE dataset contains industrial requirements reviewed for quality defects. The study uses it to evaluate how the frozen screening model transfers to a different dataset and annotation scheme.

Dataset URL
https://zenodo.org/records/16049822

Download the datasets from their original sources and follow their access, licensing, and redistribution terms.

The supplementary file pilot_consensus.csv contains the anonymized final consensus labels for all 63 candidates in the human pilot.

Research Workflow

1. Data Preparation and Ambiguity Screening

The SRS study checks requirement texts for duplicates and conflicting labels before model evaluation. Screening models classify requirements into the six categories retained from the dataset.

Screening is evaluated as a supporting study. In the ORCHID repair experiments, ambiguity targets come from the benchmark annotations.

2. Evidence Retrieval and Representation

Relevant passages are retrieved for each requirement in the repair experiment. Extracted assertions are organized in an evidence ledger that records their supporting text spans, source identifiers, project applicability, version, and approval status where available.

The experiment compares two representations of the same ledger.

* A flat representation containing assertions and provenance records
* A graph representation connecting assertions, entities, relations, and source spans

Both representations contain the same underlying evidence. Project authority is simulated in the ORCHID experiments.

3. Candidate Generation

A language model receives the original requirement, the nominated ambiguity target, and the evidence supplied by the experimental condition. It then generates a proposed rewrite.

The experiments vary whether the source parse is visible and whether the evidence ledger uses a flat or graph representation. Guard-enabled and Guard-disabled comparisons reuse the same generated candidate.

4. Guard Assessment and Release

The Guard checks whether the candidate preserves unaffected obligations, supports material changes, remains consistent with the evidence, and resolves the nominated ambiguity.

Its operational release decision combines hard eligibility checks with continuous scores.

The formal Justified Repair criterion, JR*, defines three assessment outcomes.

* Justified — The evidence is assessable and all substantive justification conditions hold.
* Unjustified — The case is assessable and at least one substantive condition fails.
* Unassessable — Governing evidence, source authority, or essential assessment inputs are insufficient.

5. Evaluation

The study reports several complementary outcomes.

* Ambiguity screening performance and transfer to QuRE
* Executable functionality of programs generated from the requirements
* Release coverage under the evaluated Guard policies
* Coverage changes when selected hard gates are disabled
* Assessor agreement and final consensus in the human pilot

The human pilot assesses baseline rewrites and reference controls. Estimating unjustified-release risk for the Guard requires independent JR* judgments on the candidates released by that policy.

Main Findings

With the Guard enabled, the strict policy released 0 of 132 test candidates in each matched setting.

On the fixed development cohort, disabling the target-resolution and contract-authorization gates increased releases at threshold zero from 1 to 43 of 132 candidates. These 43 candidates still require independent JR* assessment before their unjustified-release risk can be estimated.

In the separate human pilot, assessors judged 55 of 63 candidates, or 87.3%, to be correct repairs after adjudication.

The study provides a formal justification criterion and diagnoses where the evaluated release policy restricts coverage. ReqKG Guard can support audits by recording the evidence and checks behind a decision to withhold a proposed rewrite.

Main Notebook

The main notebook is ReqKG_with_Ui.ipynb.

Download the required datasets using the links above, configure the input paths and experiment settings, and follow the instructions in the notebook.

Funding

This research received no external funding.

Data and Code Availability

The SRS, ORCHID, and QuRE datasets are available through the original sources linked above. Access to and redistribution of these datasets are governed by the terms of their original releases.

The supplementary file pilot_consensus.csv provides the anonymized item-level consensus labels for the human pilot.

The project code repository is available at
https://github.com/sharareh2424/ReqkG
