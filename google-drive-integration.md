# Google Drive Sync & Advanced History ☁️

Google Drive synchronization provides a secondary, highly flexible layer of revision control.

---

## 🌟 Advanced Per-Page Management

Unlike standard file backups, the **Google Drive Sync Engine** in GitSync Notes creates dedicated per-page snapshot records:

1. **Per-Page History Isolation**: Each document page retains its own independent revision timeline inside Google Drive.
2. **Metadata Headers**: Drive files store structured JSON headers containing page IDs, parent-child relationships, tag arrays, and commit hashes.
3. **Restoration Capabilities**: You can inspect or pull any historic Drive snapshot directly into your local workspace.

---

## 🛠️ Setup Instructions

To activate Google Drive synchronization:
1. Open **Sync Settings** in the top navigation bar.
2. Select the **Google Drive** tab.
3. Set your target folder name (e.g., `GitSync-Notes-Backup`).
4. Toggle **Enable Auto-Backup** and **Sync History Separately**.
