# Copilot Instructions for Vouch AI

## Project Purpose
This project is an AI-assisted audit vouching workspace built inside VS Code using GitHub Copilot Agent Mode, reusable skills, and Python tools.

## Permanent Client Vault
Use:

`C:\Users\vmanm\Desktop\Vouch AI\OneDrive\Clients`

## Operating Model
Copilot Agent Mode is the agent layer.

Skills inside `.github/skills/` define the workflow.

Python scripts/tools perform actual file operations, Excel processing, validation, reconciliation, sampling, and workpaper creation.

## Key Rules
1. Always operate inside the active client workspace.
2. Never permanently delete client files.
3. Move deleted files to the client’s `99_Recycle_Bin/`.
4. Always log actions to `audit_log.json`.
5. Always update `workflow_state.json`.
6. Always resume from the first incomplete workflow stage.
7. Do not proceed to sub-ledgers before Trial Balance validation.
8. Do not reconcile before TB summary.
9. Do not sample before reconciliation.
10. Do not finalize before vouching.

## Active Workflow Skills
- audit-workflow-orchestrator
- workspace-management
- trial-balance-upload-summary
- sub-ledger-upload-preview
- trial-balance-ledger-reconciliation
- audit-sampling
- document-request
- invoice-vouching
- workpaper-finalization

## Preferred User Interaction
Use clear prompts and confirmations.

Examples:
- “Please upload the Trial Balance file now.”
- “Trial Balance is clean and balanced. Please upload sub-ledgers now.”
- “Sub-ledgers uploaded and previewed. Shall I start reconciliation?”
- “Reconciliation passed. Shall I run sampling?”
