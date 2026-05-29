# Codex Skills Install Manifest

Last updated: 2026-05-29

This file is the portable install list for this skill set. On a new device, open this file in Codex or run the script below to install the same skills globally.

## One-Click Install (Windows PowerShell)

Run this from any folder:

```powershell
$ErrorActionPreference = "Continue"

$commands = @(
  'npx skills add https://github.com/791806372-coder/KaiZZZ-s-GREAT-quality-life-Skills -g -y --copy --skill "*"',
  'npx skills add Leonxlnx/taste-skill -g -y --copy --skill "*"',
  'npx skills add pbakaus/impeccable -g -y --copy --full-depth --skill impeccable',
  'npx skills add https://github.com/ibelick/ui-skills -g -y --copy --skill baseline-ui',
  'npx skills add greensock/gsap-skills -g -y --copy --skill "*"',
  'npx skills add anysearch-ai/anysearch-skill -g -y --copy',
  'npx skills add alchaincyf/huashu-skills -g -y --copy --skill "*"',
  'npx skills add JCodesMore/ai-website-cloner-template -g -y --copy --full-depth --skill clone-website',
  'npx skills add vibeforge1111/keep-codex-fast -g -y --copy',
  'npx skills add ComposioHQ/awesome-codex-skills -g -y --copy --skill agent-deep-links brand-guidelines canvas-design changelog-generator codebase-migrate competitive-ads-extractor connect connect-apps content-research-writer create-plan datadog-logs deploy-pipeline developer-growth-analysis domain-name-brainstormer email-draft-polish file-organizer gh-address-comments gh-fix-ci helium-mcp image-enhancer internal-comms invoice-organizer issue-triage langsmith-fetch lead-research-assistant linear mcp-builder meeting-insights-analyzer meeting-notes-and-actions notion-knowledge-capture notion-meeting-intelligence notion-research-documentation notion-spec-to-implementation paperjsx pr-review-ci-fix raffle-winner-picker sentry-triage skill-share slack-gif-creator spreadsheet-formula-helper support-ticket-triage tailored-resume-generator template-skill theme-factory video-downloader webapp-testing'
)

foreach ($cmd in $commands) {
  Write-Host ""
  Write-Host "==> $cmd" -ForegroundColor Cyan
  Invoke-Expression $cmd
}

Write-Host ""
Write-Host "Done. Restart Codex to pick up new skills." -ForegroundColor Green
```

## One-Click Install (macOS / Linux)

Run this from any folder:

```bash
set +e

commands=(
  'npx skills add https://github.com/791806372-coder/KaiZZZ-s-GREAT-quality-life-Skills -g -y --copy --skill "*"'
  'npx skills add Leonxlnx/taste-skill -g -y --copy --skill "*"'
  'npx skills add pbakaus/impeccable -g -y --copy --full-depth --skill impeccable'
  'npx skills add https://github.com/ibelick/ui-skills -g -y --copy --skill baseline-ui'
  'npx skills add greensock/gsap-skills -g -y --copy --skill "*"'
  'npx skills add anysearch-ai/anysearch-skill -g -y --copy'
  'npx skills add alchaincyf/huashu-skills -g -y --copy --skill "*"'
  'npx skills add JCodesMore/ai-website-cloner-template -g -y --copy --full-depth --skill clone-website'
  'npx skills add vibeforge1111/keep-codex-fast -g -y --copy'
  'npx skills add ComposioHQ/awesome-codex-skills -g -y --copy --skill agent-deep-links brand-guidelines canvas-design changelog-generator codebase-migrate competitive-ads-extractor connect connect-apps content-research-writer create-plan datadog-logs deploy-pipeline developer-growth-analysis domain-name-brainstormer email-draft-polish file-organizer gh-address-comments gh-fix-ci helium-mcp image-enhancer internal-comms invoice-organizer issue-triage langsmith-fetch lead-research-assistant linear mcp-builder meeting-insights-analyzer meeting-notes-and-actions notion-knowledge-capture notion-meeting-intelligence notion-research-documentation notion-spec-to-implementation paperjsx pr-review-ci-fix raffle-winner-picker sentry-triage skill-share slack-gif-creator spreadsheet-formula-helper support-ticket-triage tailored-resume-generator template-skill theme-factory video-downloader webapp-testing'
)

for cmd in "${commands[@]}"; do
  echo ""
  echo "==> $cmd"
  eval "$cmd"
done

echo ""
echo "Done. Restart Codex to pick up new skills."
```

## Installed Groups

### Personal Repository

Source:

```text
https://github.com/791806372-coder/KaiZZZ-s-GREAT-quality-life-Skills
```

Installs all skills in this repo:

- `daily-share-feedback`
- `live-share-feedback`
- `share-feedback-review`
- `cyberpunk-glitch-button`
- `knowledge-html-site`

### Taste / UI Design Skills

- `Leonxlnx/taste-skill`: install all 13 sub-skills.
- `pbakaus/impeccable`: install the `impeccable` skill and its references/scripts.
- `ibelick/ui-skills`: install only `baseline-ui`.
- `greensock/gsap-skills`: install all GSAP sub-skills.

### Search / Website / Maintenance

- `anysearch-ai/anysearch-skill`
- `JCodesMore/ai-website-cloner-template`: `clone-website`
- `vibeforge1111/keep-codex-fast`

### Huashu Skills

- `alchaincyf/huashu-skills`: install all Huashu sub-skills.

### Composio Awesome Codex Skills

Only the selected top-level skills are installed. Do not use `--skill "*"` on this repo unless you intentionally want hundreds of app-specific `composio-skills/*` entries.

Selected top-level skills:

```text
agent-deep-links brand-guidelines canvas-design changelog-generator codebase-migrate competitive-ads-extractor connect connect-apps content-research-writer create-plan datadog-logs deploy-pipeline developer-growth-analysis domain-name-brainstormer email-draft-polish file-organizer gh-address-comments gh-fix-ci helium-mcp image-enhancer internal-comms invoice-organizer issue-triage langsmith-fetch lead-research-assistant linear mcp-builder meeting-insights-analyzer meeting-notes-and-actions notion-knowledge-capture notion-meeting-intelligence notion-research-documentation notion-spec-to-implementation paperjsx pr-review-ci-fix raffle-winner-picker sentry-triage skill-share slack-gif-creator spreadsheet-formula-helper support-ticket-triage tailored-resume-generator template-skill theme-factory video-downloader webapp-testing
```

## Optional: OpenSpec

OpenSpec is installed as a CLI, not through `npx skills add`.

```powershell
npm install -g @fission-ai/openspec@latest
openspec init
```

Expected generated skills include:

- `openspec-explore`
- `openspec-propose`
- `openspec-apply-change`
- `openspec-archive-change`

Run `openspec init` inside the workspace where you want OpenSpec project files.

## Verify

```powershell
npx skills ls -g --json
```

Then restart Codex.

## If Network Install Fails

If `npx skills add` fails with GitHub TLS errors, rate limits, or clone timeouts, open this file in Codex on that device and ask:

```text
按照 INSTALL_SKILLS.md 安装这些 skills。如果 npx/Git clone 失败，使用 GitHub API、raw 文件或 zip/sparse fallback 完成安装。
```

This mirrors the fallback used on the original Windows machine.
