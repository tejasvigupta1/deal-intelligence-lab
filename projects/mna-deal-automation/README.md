# AI-Enabled M&A Deal Automation Platform

## Objective

Build an automated workflow that converts public M&A filings into review-ready merger models.

## Business Problem

Investment banking analysts spend substantial time reading filings, extracting transaction terms and manually populating merger models.

This project automates first-pass mechanical work while preserving analyst judgement and review.

## Architecture

The platform uses a staged workflow that moves information from a public SEC filing into a structured output and then into Excel for analyst review.

```text
SEC Filing
→ Document Classification
→ Transaction Extraction
→ JSON Output
→ Validation Checks
→ Excel Model Population
→ Analyst Review
```

The documented technology stack for this architecture includes Python, the Claude API, Microsoft Copilot, Excel, `openpyxl`, JSON and SEC EDGAR.

## Seven-Transaction Validation Scope

Version 1 was validated across seven public M&A transactions:

- 5 completed transactions
- 1 terminated transaction
- 1 blocked transaction

The validation scope spans completed, terminated and blocked outcomes while keeping the source material within public M&A filings.

## Workflow Controls

The documented workflow includes several controls before an output is treated as review-ready:

- Document classification before transaction extraction
- Structured JSON output between extraction and model population
- Validation checks before the Excel model is populated
- Analyst review as the final workflow stage

These controls separate first-pass automation from analyst judgement.

## Analyst Review

The platform is designed to automate mechanical first-pass work, not replace analyst review.

Analyst review remains the final stage after validation checks and Excel model population.

## Simplified Illustrative JSON Output

The example below is illustrative and simplified. It shows the role of JSON in the documented workflow; it is not a record from any of the seven validation transactions.

```json
{
  "source_document": "Public SEC filing",
  "document_classification": "Illustrative classification",
  "transaction_terms": {
    "field_name": "Illustrative extracted value"
  },
  "validation_status": "Illustrative review status"
}
```

## Illustrative Workflow Pseudocode

The pseudocode below is illustrative and follows the documented workflow stages.

```text
filing = receive_public_SEC_filing()
classification = classify_document(filing)
transaction_terms = extract_transaction_terms(filing, classification)
json_output = structure_as_JSON(transaction_terms)

run_validation_checks(json_output)
populate_Excel_model(json_output)
route_to_analyst_review()
```

## Deliverables

- Structured JSON output containing extracted transaction terms
- A populated, review-ready Excel merger model

## Technology Stack

- Python
- Claude API
- Microsoft Copilot
- Excel
- openpyxl
- JSON
- SEC EDGAR

## Limitations

- Version 1 was validated across seven public M&A transactions; the documented validation scope does not extend beyond those transactions.
- The documented source scope is public M&A filings; no confidential data is presented in this README.
- The output is review-ready, not review-free: analyst judgement remains part of the process.
- The illustrative JSON and pseudocode above explain the workflow and are not unpublished validation results or production outputs.

## Current Status

Version 1 complete.
