---
description: Publish this project to a GitHub repo - README, About section, GitHub Pages, CI/CD, with a sensitive-data check first
argument-hint: <owner/repo> [branch=main]
---

Publish this project to the GitHub repository given in `$ARGUMENTS` (format `owner/repo`, optional second word = target branch, default `main`). If `$ARGUMENTS` is empty or not in that form, ask the user for the repo and stop until you have it.

Work through the steps in this order. Do them yourself; report each step's outcome at the end. If a step cannot be done with the tools available, say exactly what failed and give the user the manual steps. Never claim a step is done that you did not verify.

## Tooling
- Prefer the `mcp__github__*` tools (load them with ToolSearch if needed). If `gh` is installed and authenticated, it may be used for the repo settings in steps 5 and 7.
- If the target repo is not reachable (e.g. "need push access" from `add_repo`), stop and tell the user to connect GitHub at https://claude.ai/connect-github and install the Claude GitHub App on the owner. Do not work around it.
- Do not open a pull request unless the user asks. Do not push to a branch other than the target branch.

## 1. Sensitive-data check (BEFORE anything is pushed)
- Scan every tracked and untracked file that would be uploaded (use Grep, and `git ls-files`). Look for: email addresses (especially in `FORMSUBMIT_ENDPOINT`), API keys, tokens, passwords, private keys, `.env` files, internal hostnames/IPs, real names or phone numbers, and real company branding.
- This project must ship with the placeholder `YOUR_EMAIL@example.com`; if a real email address is in `FORMSUBMIT_ENDPOINT`, replace it with the placeholder (tell the user) rather than publishing it.
- Ensure no scratch files (screenshots, logs, scratchpad output) are staged. Add a `.gitignore` if useful.
- If anything sensitive is found that you cannot safely remove, STOP and ask the user. Report what the scan covered and what it found, even when clean.

## 2. README.md
Create or update `README.md` (keep any good existing content). Include: what the app is (fictitious bank IT PMO Kanban demo/training tool), a feature list, how to run (double-click `index.html`, no server), the `FORMSUBMIT_ENDPOINT` config and its one-time activation email, a note that data is in-memory only and resets on refresh, a disclaimer that it is not affiliated with or imitating any real bank, and the live Pages URL once known (step 7 fills it in). Base it on `index.html` and `CLAUDE.md`; do not invent features.

## 3. CI/CD via GitHub Actions
Create or update `.github/workflows/pages.yml` that deploys to GitHub Pages on push to the target branch and on `workflow_dispatch`, using `actions/checkout`, `actions/configure-pages`, `actions/upload-pages-artifact` and `actions/deploy-pages` with permissions `contents: read`, `pages: write`, `id-token: write`, and publishing only the site files (`index.html`) from a staging folder. Use the target branch name from the arguments in the trigger. Keep any existing workflow if it already does this.
If a lightweight check is worthwhile and needs no dependencies (e.g. confirming `index.html` exists and contains no `localStorage`/`sessionStorage`/`!important`), add it as a step before the upload; do not add npm or a build step.

## 4. Push the code
- Add the remote if missing (`origin` for the target repo), commit the changes with a clear message (follow the repo's attribution rules), and push to the target branch with `git push -u origin <branch>`; on network errors retry up to 4 times with backoff (2s, 4s, 8s, 16s).
- If the target branch is protected or the push is rejected, report it; never force-push.
- Confirm with the user before the push if the repo is not the one this session was started on.

## 5. GitHub Pages
Enable Pages with source "GitHub Actions" (e.g. `gh api -X POST repos/<owner>/<repo>/pages -f build_type=workflow`, or `-X PUT` if it already exists). If you cannot, tell the user: Settings -> Pages -> Source -> GitHub Actions. Check the Actions run for the deploy and report its status. The expected URL is `https://<owner>.github.io/<repo>/`. Only report the URL as live after you have confirmed the deployment succeeded; otherwise say it is expected but unverified.

## 6. Verify
Confirm the deploy workflow run succeeded (or report the failure with logs) and, if reachable, that the Pages URL responds with 200.

## 7. GitHub About section
Update the repo's About section: description (one line, e.g. "Demo Kanban board for a fictitious bank's IT PMO - vanilla HTML/CSS/JS, single file"), topics (e.g. `kanban`, `project-management`, `vanilla-js`, `github-pages`, `demo`), and **website = the GitHub Pages URL** from step 5 (this is why this step comes last). Use `gh repo edit <owner>/<repo> --description ... --homepage ... --add-topic ...` or `gh api`. If neither is available, give the user the exact text to paste into the About gear in the repo sidebar, including the Pages URL. Then update the README's live link if it was a placeholder and push that change.

## Final report
List per step: done / done-with-caveat / not done, with links (repo, Actions run, Pages URL). Flag anything the user must do manually.
