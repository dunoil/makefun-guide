# bring-the-humans-02 — submission checklist

Competition: **bring-the-humans-02** ("Bring the humans again"), $1,000 over 50 places.
Window: opened **2026-11-18 10:30 UTC**, entries close **2026-11-21 10:30 UTC** (18:30 WITA).
Score: **verified human signups** bound to our referral code in the window. Final check ends
2026-11-22 16:30 UTC. Ties on verified signups go to the **earlier** final submission — submit as
early as this list is complete; resubmit only for real fixes/improvements.

Our referral link: **https://make.fun/r/439h2tg6** · code **`439h2tg6`** (already in README.md).

## ⛔ Blocker 1 — link GitHub to the make.fun account (owner action, cannot be done by the agent)

- [ ] On make.fun, signed in as **@pasticair-terusan**: Profile → link **GitHub**, and link the
      **@dunoil** account.
- Why it is absolute: this bounty's `repo_owner` check requires the guide repository's GitHub owner to
  be the GitHub account **linked** to the make.fun account. Unlike other bounties, a
  `.makefun/owner.json` claim file does **not** satisfy it, and source bundles are refused. No link =
  no valid entry, full stop.

## Publish the repository (after Blocker 1)

- [ ] Create a **public** GitHub repository under **github.com/dunoil** (creation time is after the
      2026-11-18 10:30 UTC opening, as required). Suggested name: `makefun-guide`.
- [ ] Fill the badge placeholders in `README.md`: replace `{{GITHUB_OWNER}}` → `dunoil` and
      `{{REPOSITORY}}` → the repo name, in the rank/reward badge URLs (lines 2–3). No `{...}`
      placeholder may remain in those URLs.
- [ ] Push this folder's contents: `README.md`, `LICENSE`, `docs/`, this checklist. **Never** add a
      `.github/README.md` (GitHub would show it instead of the guide; the entry is refused).
- [ ] Set the GitHub **About** (check: `repo_about`):
      website = `https://make.fun/bounty/bring-the-humans-02`, topics must include `makefun`.
      ```sh
      gh repo edit dunoil/<repo> \
        --description "A plain-language getting-started guide to make.fun: how AI coding agents enter bounties and earn USDC on Solana. Built by an AI agent for make.fun's 'Bring the humans again' bounty." \
        --homepage "https://make.fun/bounty/bring-the-humans-02" \
        --add-topic "makefun,ai-agents,bounties,guide"
      ```

## The screenshot (after publishing — see docs/SCREENSHOT-GUIDE.md)

- [ ] Open the published repo page on GitHub, README rendered, window ~1280 px wide, top of page.
- [ ] Full-page capture at **1x scale**; save as **`screenshot.png` at the repository root**.
- [ ] Verify: PNG/JPEG/WebP, ≤ 8 MB, ≤ 16,000,000 pixels, top shows repo name + start of the guide.
- [ ] Commit and push it. **Do not fabricate or reuse the kit starter's sample screenshot.**

## Bundle, check, submit (parent agent, from the top-level session)

- [ ] Bundle transcripts (this build's sessions + parent chats, `--muse-usage` rows attached, system
      prompt uploaded, personal details redacted) per `~/workspace/makefun/PLAYBOOK.md`:
      ```sh
      cd ~/workspace/makefun/kits/bring-the-humans-kit/bring-the-humans-02-kit
      node cli/makefun.mjs bundle --repo <repo-dir> --out transcripts.tar.gz [playbook flags]
      ```
- [ ] Local check must pass everything, incl. `guide_page`, `repo_readme`, `repo_about` and the
      11-check transcript gate:
      ```sh
      node cli/makefun.mjs check --kit . --repo <repo-dir> --transcripts transcripts.tar.gz
      ```
- [ ] Submit (signed entry message is valid 10 minutes; signing wallet = agent wallet, the payout
      wallet):
      ```sh
      node cli/makefun.mjs submit --competition bring-the-humans-02 \
        --repo-url https://github.com/dunoil/<repo> --commit <sha> \
        --title "make.fun, from zero to your first USDC — a getting-started guide" \
        --bundle transcripts.tar.gz --keypair ~/workspace/makefun/agent-keypair.json
      ```
- [ ] Record the submission id + claim code in a `SUBMISSION.md` beside the entry (never in memory).
- [ ] Quotas: max **5 submissions per UTC day, 10 total**; the latest one before the deadline is the
      final entry.

## After submitting — actually bringing the humans

- [ ] Share **https://make.fun/r/439h2tg6** where developers read (the guide repo itself, posts,
      communities). Signups count only if they are real new people who take part: our own accounts,
      same-network signups, IP clusters, idle/lurker accounts and bots are all filtered out by the
      house referral check — do not attempt any of those; they count for nothing and risk the entry.
- [ ] **Final re-check survival:** keep the repo public, the same repository, under the same GitHub
      account, with code `439h2tg6` still in the default branch's `README.md`, until results publish
      (final phase ends 2026-11-22 16:30 UTC). A rename that redirects is fine; going private,
      deleting, or stripping the code disqualifies the entry.
- [ ] If placed: claim from the escrow with `makefun status` → `makefun claim --claim <id>
      --keypair ~/workspace/makefun/agent-keypair.json` (prizes: 1st $150, 2nd $80, 3rd $50,
      4th–10th $20, 11th–25th $17, 26th–50th $13).
