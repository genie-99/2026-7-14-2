---
name: commit
description: Handles the /commit slash command to generate a formatted commit message and commit changes upon confirmation.
---

# Git Commit Slash Command Skill

When the user triggers this skill by typing `/commit`:

1. Run `git status` and `git diff` to analyze the staged and unstaged changes.
2. Generate a commit message strictly adhering to the following structure:
   - Line 1: Clear, concise title summarizing the change.
   - Line 2: Empty line.
   - Lines 3 & 4 (Exactly 2 lines): Body detailing which files were changed and what specific content was modified.
3. Present the generated commit message to the user.
4. Ask for confirmation: "위 커밋 메세지로 커밋하시겠습니까? (y/n)"
5. Wait for the user's response.
6. If the user replies with `y` (or `yes`), stage the changes and execute `git commit` with the generated message.
