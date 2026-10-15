# Intervia AI — Ultra Luxury Premium Edition

Release date: 15 October 2026

## UI theme update
- Aligned the visual palette with the supplied dashboard reference: obsidian/midnight navy surfaces, sapphire blue panels, ice-cyan borders and accents, platinum-white typography.
- Refined the hero, cards, metrics, tabs, buttons, upload controls, inputs, expanders and focus states.
- Standardized input surfaces to light backgrounds with dark text for readability.
- Removed build/test cache directories from the distribution package.

## Functionality policy
This release changes presentation styling and Streamlit theme configuration; it does not intentionally remove interview workflows, agents, evidence processing, ATS readiness, session handling, scoring, or report generation.

## Validation
- Python syntax compilation passed.
- `python verify_project.py` passed.
- `pytest -q`: 17 passed.
- ZIP integrity and fresh extraction checks performed after packaging.

A live Streamlit browser run and real Groq API call were not performed as part of this package validation.
