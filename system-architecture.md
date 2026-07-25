# System Architecture & Sync Flow 🏗️

This page documents how **GitSync Notes** handles per-page version control and sync workflows.

---

## 📐 Data Pipeline & Version Control

```
[ Markdown Editor ] ──(Auto-Save / Commit)──> [ Local Commit Memory ]
                                                      │
                       ┌──────────────────────────────┴──────────────────────────────┐
                       ▼                                                             ▼
         [ GitHub REST API Sync ]                                      [ Google Drive Revision Manager ]
     • Writes markdown files in repo                                 • Stores per-page snapshot files
     • Inline commit timeline & dates                                • Independent per-page change control
```

## 🔄 Dual Sync Mechanism Comparison

| Service | Primary Purpose | Change Tracking Method |
| :--- | :--- | :--- |
| **GitHub** | Code repository alignment | Commits pushed to repository branch matching local timestamp |
| **Google Drive** | Standalone cloud archive | Granular revision snapshots per page in cloud storage folder |

### Auto-Commit Lifecycle
1. User edits Markdown in the editor.
2. System computes diff against the last commit.
3. If changes exceed threshold, a new snapshot hash is generated (`git-short-hash`).
4. Visual Diff Viewer computes additions (`+`) and deletions (`-`).
5. Sync queues upload to GitHub and Google Drive.
