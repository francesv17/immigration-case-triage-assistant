# Immigration Case Triage Assistant

### AI-Assisted Legal Workflow Prototype

**Created by Frances V. Perez, Esq.**

## Overview

The Immigration Case Triage Assistant is an experimental legal-engineering prototype exploring how generative AI can support the initial organization and triage of immigration client intake information while preserving attorney judgment and human review.

The system converts an unstructured client intake narrative into structured case information, validates the AI-generated output, identifies missing or conflicting facts, applies deterministic Python triage rules, and generates an attorney-facing review report.

This project uses synthetic client scenarios only and is not intended to provide legal advice or make legal eligibility determinations.

## System Architecture

The prototype separates probabilistic AI tasks from deterministic workflow logic:

**Client Intake Narrative**  
↓  
**AI Fact Extraction**  
↓  
**Structured Case Data**  
↓  
**Schema & Type Validation**  
↓  
**Deterministic Triage Rules**  
↓  
**Attorney Review Report**  
↓  
**Human Attorney Judgment**

The AI layer is used primarily for language understanding and structured fact extraction. Predictable workflow decisions are handled through deterministic Python rules.

## Key Design Principles

- Preserve unknown information rather than guessing.
- Surface contradictory facts rather than asking the model to resolve them.
- Separate AI-generated extraction from deterministic workflow logic.
- Validate AI output before downstream processing.
- Flag issues for attorney review rather than making legal eligibility determinations.
- Keep human attorney judgment as the final decision-making layer.

## Evaluation

Prompt iterations were tested against synthetic immigration intake scenarios designed to expose uncertainty, contradictions, entity-attribution problems, incomplete dates, unsupported inference, and structured-output failures.

During development regression testing, Prompt V5 produced **63/64 correct factual fields (98.4%)** across Test Cases 3–6.

A later validation run of the finalized prototype produced **64/64 factual fields (100.0%)** on the same small synthetic test set.

These are run-specific experimental benchmarks and should not be interpreted as general model accuracy on immigration matters or real-world client files.

## What This Project Demonstrates

- Legal workflow analysis and decomposition
- Prompt engineering and iterative failure analysis
- Structured AI fact extraction
- Schema and data-type validation
- Deterministic Python workflow logic
- Attorney-defined evaluation benchmarks
- Regression testing
- Human-in-the-loop AI design
- Legal-domain safeguards and uncertainty handling
- Development of an interactive attorney-facing prototype

## Technology

- Python
- OpenAI API
- JSON
- Google Colab
- Gradio

## Running the Prototype

1. Open `Immigration_Case_Triage_AI_Workflow.ipynb` in Google Colab.
2. Add an OpenAI API key to **Colab Secrets** using the name `OPENAI_API_KEY`.
3. Run the notebook cells.
4. Use only synthetic or non-confidential information when testing the prototype.
5. Enter a synthetic immigration intake narrative in the Gradio interface and select **Analyze Case**.

API credentials are not stored in this repository.

## Limitations

This is an experimental portfolio prototype, not a production legal system. The evaluation set is intentionally small and synthetic. The system does not independently verify client facts, provide legal advice, determine eligibility for immigration relief, or replace attorney review.

Additional development would be required for production deployment, including broader evaluation, security and privacy review, expanded validation, monitoring, and testing across a substantially larger set of scenarios.

## Data & Confidentiality

All client scenarios used in this project are synthetic. No confidential client information is included.
