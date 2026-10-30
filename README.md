# TAIG Hammer Game - PN

Original grimdark sci-fi dice game. Solo, offline, no spend, no online play, no AI rolls.

Built to ACI-TAIG-HAMMER-001, dice-only playable version, start to finish. No borrowed names, factions, gods, iconography, slogans, lore, or art. No licence claim, and no affiliation with any other game company.

## Playable v1 — dice only

File: `hammer-game-dice-v1.html`

Open that file in a browser. No server, no install, no account.

### How to play, in plain words

You are at a wrecked transport in the rust yards. The salvage is inside. A raider is watching the far side. The way out is a jammed hatch.

Your job: finish the job and get out alive.

- Pick an action: Search the wreck, Sneak past the raider, Shoot the raider, or Fix the jammed hatch and exit.
- The game rolls a d20, adds your skill bonus, and checks it against the target number.
- Natural 20 = crit success, natural 1 = crit fail, before bonuses. Otherwise, total at or over the target = success.
- Every result shows, in order: what you tried, what you rolled, your modifier, your total, the target, and the outcome.
- You win when salvage is found and you fix the jammed hatch and exit. The win screen says: "Job done. You got out alive."
- You lose if your health runs out. The lose screen says: "Run over. Health out."
- Side goals, not required to win: find supplies, keep health and gear in shape. Gear condition is shown and tracked, but never causes a loss in v1.

### Exact numbers

Starting state: Health 20/20, Supplies 3, Gear 100%, Salvage not found, Raider watching, Roll log empty.

- Search the wreck: Search +3, target 12. Success = salvage found. Crit = salvage found + 1 supply. Fail = nothing. Crit fail = nothing, -2 health, gear -10%.
- Sneak past the raider: Sneak +2, target 14. Success = raider avoided. Crit = raider avoided + 1 supply. Fail = spotted, -5 health. Crit fail = spotted, -5 health, gear -10%.
- Shoot the raider: Shoot +3, target 13. Success = raider down. Crit = raider down + 1 supply, no damage. Fail = miss, -4 health. Crit fail = miss, -4 health, gear -10%.
- Fix the jammed hatch and exit: Fix +2, target 11. If salvage is not found, no roll — "You have not got the salvage yet. Search the wreck first." Success or crit with salvage = win. Fail = hatch stays jammed, -2 health. Crit fail = hatch stays jammed, -2 health, gear -10%.
- Use a supply: no roll, +5 health up to 20, uses 1 supply. At 0 supplies: "No supplies left.", nothing changes.
- Play again resets exactly to the starting state above.

### Board and design docs

- `board-look.html` — the single combined board: locked v1 rules, board look spec, dev dashboard, full data flow, how the game is played, board rules, and next step. This is the dashboard for this build.
- `dev-dashboard-and-data-flow.md` — source text for the dashboard and data flow.
- `ACI-TAIG-HAMMER-001.md` — the build instruction this version was built to, kept locally (not in the public repo snapshot, to keep the game repo clean).

Board look, locked: charcoal/bone/rust palette, flat hard-edged panels, uppercase headings, monospace readouts, no bright white / SaaS blue / neon, no borrowed iconography.

### What is NOT in v1

No second mission, no second map, no levels, no campaign, no character creation, no levelling, no enemies beyond the one raider, no inventory beyond supplies, salvage, and gear condition, no sound, no animation, no 3D, no accounts, no online play, no sharing scores.

### Test engineer

Cole (Q-ball Jax) is Tee's designated test engineer. Acceptance is not on record yet — no message to Cole until Tee says so. Do not mark anything "done" until Tee has actually played it.
