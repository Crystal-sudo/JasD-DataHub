 JasD DataHub Simulation: Intelligence Studio

A browser-based project for designing and grading data-validation challenges: generate a flawed dataset, define the correct final state, and score a submission against a 36-criterion rubric with a full audit trail.

Everything runs in your browser. No files are uploaded anywhere. Saved state lives in your browser's local storage.

What's included

| File | Purpose |
|
| index.html | The app (single file: HTML, CSS and JavaScript) |
| jas.png | Logo (small, optimized) |
| JasD-Task-Pack-001-Invoice-Reconciliation.zip | Sample deliverable: Task Pack 001 |

 Task Pack 001 · Invoice Reconciliation

A worked example of a complete evaluation task:

- 01_scenario_brief.md: the scenario and cleaning rules
- 02_invoice_register_FLAWED.csv: 43 rows with 27 seeded errors
- 03_po_register.csv: approved purchase orders to reconcile against
- 05_answer_key_final_state.csv: the correct 40-row final state
- 06_error_register.csv: every seeded error, its expected fix and the rule
- 07_grading_rubric.csv: 36 criteria, each with a pass definition

Seeded error types: blank values, non-ISO dates, currency text in amounts, padded whitespace, inconsistent status wording, vendor typos, duplicate invoices, and invoices exceeding their PO (which should be set to On Hold).

 How to use the app

Open Intelligence Studio from the sidebar. It has six tabs:

| Tab | Use it to 

| Overview | See status and stats |
| Document Intelligence | Upload CSV, Excel, PDF or Word files and run verification |
| Challenge Generator | Create a flawed dataset with the error types you choose |
| Grade Submission | Score a corrected CSV against an answer key |
| Advanced Evaluation | Manage the expected state and the rubric |
| Cloud Edition | Optional Firebase saving (can be ignored) |

Build a challenge

1. Open Challenge Generator and choose the error types.
2. Click Generate Dirty Dataset, then Download CSV.
3. Click Load into Evaluation to set the expected state.
4. In Advanced Evaluation, click Evaluate, then Export Report.

 Grade a submission

1. Open Grade Submission.
2. Load the answer key CSV.
3. Optionally load the original flawed CSV (this enables the "errors fixed" rate).
4. Load the submission CSV and click **Grade**.
5. Review the score, errors fixed, valid cells broken, missing/extra rows and the table of differences. Use Export report to save it as JSON.

Rows are matched by the first column (the ID), so the answer key and submission must share that column and the same headers.

Quick practice run

Load the Task Pack 001 answer key and flawed file, then grade the flawed file as the submission. It should score low (about 46%). Fix a few cells in a spreadsheet, save as CSV, and grade again to watch the score rise.

 Scoring

The score combines three things: the share of seeded errors fixed (50%), overall cell accuracy (30%), and a penalty for damage such as changing valid cells, missing rows or leftover duplicates (20%). Some rubric criteria are marked manual and need a reviewer.


Limitations

- Demonstration tool, not a production system.
- Saved data is per browser; clearing browser data resets it.
- Grade Submission compares CSV files only.
