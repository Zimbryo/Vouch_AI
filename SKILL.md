# Workspace Management Skill

## Purpose
Manage audit client workspaces inside the permanent OneDrive client vault.

Permanent base folder:
C:\Users\vmanm\Desktop\Vouch AI\OneDrive\Clients

## Core Rules
1. Never permanently delete files from a client folder.
2. When the user asks to delete/remove a file, move it to:
   99_Recycle_Bin/
3. Maintain one recycle bin inside each client folder.
4. Every create, open, delete, restore action must be recorded in audit_log.json.
5. Client folders must be created under financial year folders.

## Standard Client Structure

FY_YYYY_YY/
└── Client_Name/
    ├── 01_Trial_Balance/
    ├── 02_Ledgers/
    ├── 03_Sampled_Items/
    ├── 04_Documents/
    ├── 05_Workpapers/
    ├── 06_Final_Report/
    ├── 07_Email_Requests/
    ├── 99_Recycle_Bin/
    ├── client_config.json
    └── audit_log.json

## Commands to support

### Create client
Ask for:
- Financial year
- Client name
- Planning materiality
- Performance materiality

Then create workspace.


### Open client
List available financial years and clients.
### Update Client Config & Materiality

Ask for:
- Planning Materiality
- Performance Materiality

Then update `client_config.json`.

Rules:
1. Performance Materiality must always be less than Planning Materiality.
2. Never overwrite previous values without logging.
3. Log all updates inside `audit_log.json`.
4. Preserve historical materiality changes for audit traceability.
5. Validate that both values are numeric and greater than zero.

Actions:
- Read existing `client_config.json`
- Update:
  - `planning_materiality`
  - `performance_materiality`
- Append change entry to `audit_log.json`
- Confirm updated values to the user

### Show workspace
Display active workspace path and folders.

### Delete file safely
Move selected file to client's 99_Recycle_Bin folder.
Never use permanent delete.

### Restore file
Move file from 99_Recycle_Bin back to original location if known.

## Safety
If the file is outside the active client workspace, do not move it.
Ask user to confirm the correct workspace.