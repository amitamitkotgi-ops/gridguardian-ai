# SOLARIS AI — Development Environment Setup

## Current baseline
- OS: Windows 11
- IDE: Google Antigravity
- Language: Python
- Backend direction: FastAPI
- Database: SQLite
- Embedded: ESP32 Arduino framework or ESP-IDF after board choice is confirmed
- Existing dashboard and simulator: audit before changing
- Version control: Git + GitHub

## Local repository setup
Open PowerShell in the cloned repository:

    git status
    git switch main
    git pull
    git switch --track origin/solaris-ai/phase-0-foundation

If the branch already exists locally, use:

    git switch solaris-ai/phase-0-foundation

Create/activate the Python environment only after checking the existing Python version and requirements:

    py --version
    py -m venv .venv
    .\.venv\Scripts\Activate.ps1
    python -m pip install --upgrade pip

Do not replace the repository dependency file until its current contents and imports have been audited.

## Environment and secrets
- Keep credentials in local .env files.
- Commit .env.example with placeholder names only.
- Confirm .env, database files, generated telemetry and local secrets are ignored by Git where appropriate.
- Never paste API keys into source code or commit history.

## Baseline verification
Before code changes:
1. Record Git status and current commit.
2. Read README and existing project structure.
3. Run existing tests, if present.
4. Start the existing app using its documented command.
5. Record known failures separately; do not silently rewrite the app.

## Antigravity project skills
Project-specific skills live under .agents/skills/<skill-name>/SKILL.md. After checking out this branch, Antigravity IDE can discover committed skills. If Antigravity is already open, reload skills or start a new agent conversation.

Official guide: https://antigravity.google/docs/skills
