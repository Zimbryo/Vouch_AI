Building AI Audit Lab — Demonstrating Agentic AI Purchase Vouching
Project Overview
AI Audit Lab is a practical project developed to explore how Agentic AI can assist in audit workflows, audit evidence management, and purchase vouching procedures in a structured and traceable manner.
The project demonstrates how AI-assisted workflows can help organize:
Trial Balance validation
Ledger classification
Audit sampling
Supporting document management
Document summarization
Purchase vouching
Audit workpaper preparation
The focus of the current demo is:
End-to-End Purchase Vouching Workflow

using:
VS Code
GitHub Copilot Agent Mode
Python
AI-assisted workflow orchestration
The project is designed as a local-first audit lab and proof-of-concept rather than a production ERP or audit platform.

Core Objective
The objective of the project is to demonstrate how Agentic AI can assist auditors in:
Structuring audit workflows
Organizing audit evidence
Reducing repetitive manual effort
Improving audit traceability
Supporting audit vouching procedures
Generating audit-ready workpapers
while keeping audit judgment and professional skepticism under auditor control.

Technology Stack
Development Environment
VS Code
GitHub Copilot Agent Mode
Processing Layer
Python
pandas
openpyxl
Storage
OneDrive synced local folders
AI Layer
OpenAI-compatible APIs
NVIDIA AI APIs
Local LLM 
Document Handling
PDF text extraction
OCR-ready architecture
Excel processing

Workspace Architecture
Each audit client is automatically organized into a structured workspace:
Clients/
└── FY_2025_26/
    └── Client_Name/
        ├── 01_Trial_Balance/
        ├── 02_Ledgers/
        ├── 03_Supporting_Documents/
        ├── 04_Sampled_Items/
        ├── 05_Workpapers/
        ├── 06_Final_Report/
        ├── 99_Recycle_Bin/
        ├── workflow_state.json
        ├── client_config.json
        └── audit_log.json

The system automatically:
Creates folders
Maintains workflow states
Tracks audit actions
Supports resume-aware workflows
Prevents permanent deletion using recycle bins

Agentic Skill-Based Architecture
The project uses modular AI skills to simulate audit workflow orchestration.
Skills Structure
.github/skills/
├── audit-workflow-orchestrator/
├── workspace-management/
├── trial-balance-upload-summary/
├── sub-ledger-identification-classification/
├── document-upload-classification/
├── document-summarizer/
├── purchase-vouching/
├── audit-sampling/
├── reconciliation/
└── workpaper-generation/

Each skill handles one stage of the audit workflow.
The orchestrator controls the workflow sequence and resume logic.

Purchase Vouching Demo Workflow
The current demo showcases:
Trial Balance
    ↓
Purchase Ledger Upload
    ↓
Reconciliation
    ↓
Sampling
    ↓
Supporting Document Upload
    ↓
Document Summarization
    ↓
Purchase Vouching
    ↓
Workpaper Generation


Demonstration Flow in 5 Prompts
The purchase vouching demo is designed to work through a small number of workflow prompts.
Prompt 1 — Create New Client
User Prompt
create a new client "LMN Ltd 2026"

AI System Demonstration
Creates audit workspace for LMN Ltd 2026
Initializes audit configuration
Creates folder structure for ledgers, samples, extracted data, and workpapers
Initializes workflow tracking
Generated Structure
LMN Ltd 2026/
│
├── 01_Raw_Data/
├── 02_Samples/
├── 03_Extracted_Data/
├── 04_Documents/
├── 05_Workpapers/
├── workflow_state.json
└── audit_config.json


Prompt 2 — Upload Trial Balance and Generate Summary
User Prompt
C:\Users\vmanm\Desktop\Purchase Vouching - Copy\TB.xlsx upload TB and do summary

AI System Demonstration
Uploads Trial Balance Excel file
Validates ledger structure and debit-credit balancing
Identifies purchase-related ledgers
Performs financial summary analysis
Detects unusual balances and risk indicators
AI Output
TB_Summary_Report.xlsx

Summary Includes
Total debits and credits
Major purchase ledgers
GST balances
Expense analysis
High-risk ledger identification

Prompt 3 — Upload Purchase Ledger and Perform Sampling
User Prompt
C:\Users\vmanm\Desktop\Purchase Vouching - Copy\purchase_ledger.csv upload purchase ledger and do sampling

AI System Demonstration
Imports purchase ledger CSV
Cleans and standardizes transaction data
Detects duplicates and anomalies
Performs AI-based audit sampling
Sampling Logic
High-value transactions
Random sampling
GST risk sampling
Month-end transactions
Unusual vendor analysis
AI Output
Purchase_Samples.xlsx

Sample Output Example
Invoice No
Vendor
Amount
Sampling Reason
INV-1021
ABC Traders
12,50,000
High Value
INV-2044
XYZ Enterprises
98,500
Random
INV-3055
PQR Metals
4,80,000
GST Risk


Prompt 4 — Upload Documents, Classify and Extract Data
User Prompt
C:\Users\vmanm\Desktop\Purchase Vouching - Copy\Samples upload documents, classify and do Extraction

AI System Demonstration
Uploads supporting documents
Automatically classifies documents using AI
Performs OCR on scanned invoices and PDFs
Extracts structured invoice and GST data
Supported Documents
Purchase Invoices
Purchase Orders (PO)
GRNs
E-Way Bills
Debit Notes
Extracted Fields
Invoice Number
Vendor Name
GSTIN
Invoice Date
Taxable Value
CGST / SGST / IGST
Total Amount
AI Validation
GST calculation verification
Duplicate invoice detection
Vendor matching
Date validation
PO/Invoice consistency checks
AI Output
Extracted_Data.xlsx

Additional Feature
Confidence scoring for extracted fields
Low-confidence fields flagged for reviewer attention

Prompt 5 — Perform Purchase Vouching
User Prompt
Perform Purchase Vouching.

AI System Demonstration
Matches ledger entries with supporting documents
Performs AI-assisted vouching procedures
Verifies audit assertions
Identifies exceptions and mismatches
Verification Performed
Audit Check
Description
Invoice Match
Ledger vs Invoice
PO Match
Invoice vs PO
GRN Match
Goods receipt verification
GST Validation
Tax accuracy
Vendor Validation
Vendor consistency

AI Exception Detection
Missing invoices
Duplicate invoices
GST mismatches
Missing GRNs
PO excess purchases
Incorrect dates
Vouching Status
Status
Meaning
Verified
No issues identified
Exception
Audit issue detected
Partial Match
Incomplete evidence
Reviewer Attention
Requires manual review

Final AI Output
Purchase_Vouching_Workpaper.xlsx

Generated Reports
Purchase Vouching Workpaper
Exception Report
Verification Summary
Audit Trail Logs


Resume-Aware Workflow
The project supports resumable workflows using:
workflow_state.json

Users can continue from the last incomplete stage without restarting the workflow.

Design Philosophy
The project separates:
Deterministic Processing
Handled using Python:
Calculations
Matching
Validation
File management
Excel processing
AI-Assisted Tasks
Handled using AI models:
Audit remarks
Exception interpretation
Document summarization
Narrative generation
This improves:
Traceability
Workflow discipline
Reliability
Token efficiency

Practical Significance
The project demonstrates how AI-assisted systems can help auditors:
Organize audit evidence
Structure audit workflows
Reduce repetitive manual procedures
Improve document traceability
Assist in audit vouching
Generate audit-ready workpapers
while still preserving professional judgment and audit control.

Future Scope & Vision
This project demonstrates the foundation of an AI-enabled Audit Lab that can evolve into a strong end-to-end audit workflow system for modern audit environments.
The architecture is designed to support significant improvements in:
Audit efficiency
Time management
Documentation handling
Audit evidence organization
Workflow traceability
Operational scalability
By combining structured audit workflows with Agentic AI, the system has the potential to reduce repetitive manual procedures involved in:
Vouching
Evidence tracking
Ledger management
Document classification
Workpaper preparation
Audit coordination
The broader vision of the project is to explore how Chartered Accountants and audit professionals can leverage Agentic AI to build practical, workflow-oriented audit systems that improve productivity, reduce operational effort, and modernize traditional audit processes.

Repository Structure
ai-audit-lab-agentic-vouching/
├── README.md
├── requirements.txt
├── .github/
│   └── skills/
├── tools/
├── sample_data/
├── outputs_sample/
└── docs/


Conclusion
AI Audit Lab is a practical attempt to explore how Agentic AI can support modern audit workflows from a Chartered Accountant’s perspective.
The project combines:
Audit process understanding
Structured workflows
Document intelligence
AI-assisted analysis
Workpaper automation
to demonstrate how AI-enabled audit systems may evolve in future audit environments while preserving audit traceability, workflow discipline, and professional judgment.

# Vouch_AI
