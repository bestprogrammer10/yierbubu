---
name: auto-git-sync
description: Automates Git sync (check, add, commit, push) when the user wants to end the session. Trigger this when the user says "bye", "exit", "done", "finish", "wrap up", or "save and quit".
---

# Auto Git Sync

This skill handles the "shutdown" protocol for the project. It ensures that no work is lost when the user is finished.

## Workflow

Follow these steps strictly when this skill is triggered.

### 1. Check Status
Execute the following command to check for pending changes:
```powershell
git status
```

### 2. Analyze & Act

**Scenario A: Clean Workspace**
If the output contains "nothing to commit, working tree clean":
1. Inform the user that everything is already saved.
2. Bid the user farewell (e.g., "Project is clean. See you next time!").

**Scenario B: Uncommitted Changes**
If the output indicates modified, deleted, or untracked files:

1. **Stage Changes**:
   ```powershell
   git add .
   ```

2. **Generate Commit Message**:
   - Run `git diff --cached` to understand the changes.
   - Create a concise, descriptive commit message (in Chinese, as per project convention) summarizing the changes (e.g., "Update story script", "Fix bug in prompt generator").
   - *Constraint*: Do not ask the user for a message. Generate a sensible one automatically.

3. **Commit**:
   ```powershell
   git commit -m "<your_generated_message>"
   ```

4. **Push**:
   ```powershell
   git push
   ```

5. **Report**:
   - Inform the user of the actions taken (e.g., "Detected changes. Staged, committed ('<message>'), and pushed to remote.").
   - Bid the user farewell.

### 3. Error Handling
- If `git push` fails (e.g., due to conflict), do **not** force push.
- Inform the user of the error and suggest they resolve the conflict manually.