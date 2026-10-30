# TAIG Hammer Game - PN
## Dev Dashboard + Game Data Flow — Start Here

Original grimdark sci-fi game. No Games Workshop names, factions, gods, iconography, slogans, lore, or art. Close enough to feel right, original enough to stay clear.

Locked rules for v1:
- Simple-first, broke-mode, offline-first
- No AI in v1 rolls
- No PvP, no gacha, no 3D, no multiplayer, no paid power
- Cole (Q-ball Jax) is Tee's designated test engineer, but his acceptance is not on record yet — no message to Cole until Tee says so

Tee's way in: learning while building. So each piece below says what it is, in plain language, before it says how to build it.

## Board look — genre match (LOCKED Oct 28 evening, preview approved by Tee)

The board should look like the game it tracks: original grimdark sci-fi, worn and industrial, not clean SaaS, not bright fantasy, not neon cyberpunk.

Palette (use these exact hexes, no other accent colors in v1):
- Background: #141210 (near-black charcoal-brown)
- Panel: #1e1b18 (dark steel-brown)
- Panel edge: #3a332c
- Main text: #d6cdb8 (bone)
- Muted text: #9a9080
- Rust amber (headings, started, highlights): #c07a2e
- Hazard amber (thin stripes only): #d9a441
- Rust red (fail / waiting / warnings): #8c3324
- Steel grey (not-started, secondary): #6b7280

Type:
- Headings: uppercase, wide letter-spacing, system condensed sans — 'Arial Narrow', 'Helvetica Neue', sans-serif. No downloaded fonts, offline-first.
- Numbers, rolls, and logs: monospace — 'Courier New', monospace. Rolls must look like a readout, not a marketing number.
- Body: plain sans, bone on charcoal. No bright white text.

Shape and texture:
- Panels: flat, 1–2px hard corners, 1px panel-edge border, thin rust top rule. No rounded cute cards, no soft pastel shadows, no glass blur.
- One thin hazard stripe per board header only — repeating diagonal amber / charcoal, 4px high. Not on every card, or it turns into wallpaper.
- Subtle worn feel from color and spacing only in v1: no photos, no borrowed iconography, no faction symbols, no double-headed birds, no skull logos, no slogans.
- Status pills: Started = amber outline, Not started = steel grey, Waiting = rust red, Done = muted bone/green only when actually tested — never bright green.

Do not:
- Do not use bright white backgrounds, clean blue SaaS palettes, or neon.
- Do not copy any Games Workshop art, symbols, names, or slogans to "make it look right" — original shapes only.
- Do not add 3D, animation, or glow in v1. The genre comes from color, type, and hard edges, not effects.

Preview LOCKED: `board-look.html` in this same folder — same dashboard content, styled with this palette, single offline file, no game code yet. Do not change the palette, type, or shape without Tee reopening the lock. Single board, Oct 28 evening (Tee: combine everything, keep it in the same board): `board-look.html` in this same folder now holds everything — dashboard, look spec, data flow, and how the game is played. The separate styled document `dev-dashboard-and-data-flow.html` is superseded by that combined board; do not update it separately.

---

## 1. Dev Dashboard — where we are

This is the dashboard for the development, not the game screen itself. It tracks what exists, what's next, and what "done" means, so nothing drifts.

| Piece | Status | What "done" means | You learn here |
|---|---|---|---|
| Dev dashboard (this file) | Started Oct 28 | You can see every piece and its status at a glance | How a build is broken into small, testable pieces |
| Board look (board-look.html) | Locked Oct 28 | Preview approved by Tee, palette/type/shape final for v1 | How genre is carried by color, type, and hard edges, not effects |
| How the game is played | Started Oct 28 | Plain-language play + objectives on the board | What the player actually does, and what winning means |
| Single board rule | Locked Oct 28 | Everything lives in board-look.html, one board only | New sections go in that file, not in separate boards |
| Game data flow (below) | Started Oct 28 | You can trace one action from button press to result on screen | How data moves through a game |
| Dice engine | Not started | Roll a d20, add a modifier, show crit / fail, keep a roll log | Random numbers, modifiers, and comparing to a target |
| Character sheet (simple) | Not started | A few stats that the dice engine can actually use | What "state" is: numbers the game remembers |
| One short mission | Decision open | Dice engine + one short run, a few checks, a pass/fail ending | How story, choices, and checks connect |
| Test with Cole | Waiting | Cole breaks it, we fix what he finds, then lock it | Testing is part of building, not after it |

Build order, learning order:
1. Dashboard + data flow (now)
2. Dice engine only — this is the common core whether the mission comes next or not
3. Simple character sheet, only the stats the engine needs
4. Then decide: stop at the engine, or add one short mission

The dice-only vs dice-plus-mission choice is still open. Nothing in steps 1–3 wastes work either way.

Development flow (how work moves here):
Idea -> ACI (written instructions for CAE) -> CAE builds it locally on Tee's laptop -> Tee tests it -> Cole tests it (when Tee says go) -> Fix -> Lock it in

One ACI at a time. Copy-paste is still the link between Muse and CAE.

---

## 2. Game Data Flow — one action, start to finish

Think of the game as a loop. The player does something, the game figures out the result, shows it, and waits for the next thing. Nothing happens by magic — data moves in a line.

```
Player picks an action
  -> Game decides what kind of check it is
  -> Roll a d20 (random 1 to 20)
  -> Add the modifier (your skill bonus, positive or negative)
  -> Compare total to the target number (called a DC, difficulty class)
  -> Decide the outcome
  -> Apply the effect
  -> Update the game state
  -> Show the result on screen
  -> Back to: player picks the next action
```

Step by step, in plain language:

1. **Player picks an action**
   Example in original terms: "Search the wreck" or "Shoot the raider."
   This is input. The game only knows what the player chose.

2. **Game decides what kind of check it is**
   Search might be a perception-style check. Shooting might be an attack check.
   Each check points to one stat / modifier. No check, no roll.

3. **Roll a d20**
   One random number, 1 to 20. Every face is equally likely.
   Special cases to learn first: a natural 20 is a critical success, a natural 1 is a critical fail — before modifiers are even added.

4. **Add the modifier**
   Total = roll + modifier.
   Example: roll 13 + modifier 3 = 16.
   The modifier is just how good your character is at that thing.

5. **Compare total to the target number (DC)**
   If total is equal to or higher than the DC, you succeed. If lower, you fail.
   Example: DC 15, total 16 = success. DC 15, total 12 = fail.
   The DC is how hard the game decided this task is. It is not random.

6. **Decide the outcome**
   Four buckets, keep them simple:
   - Critical success (natural 20)
   - Success (total meets or beats DC)
   - Fail (total below DC)
   - Critical fail (natural 1)
   Later versions can add degrees of success. V1 does not need them.

7. **Apply the effect**
   Success might mean: you find the salvage, you hit, the door opens.
   Fail might mean: you find nothing, you miss, you take damage, or the story moves a different way.
   The effect is the only place the story changes. The roll itself changes nothing until this step.

8. **Update the game state**
   State is the small box of numbers and flags the game remembers between actions:
   - Health, ammo / supplies, position or scene
   - Inventory (what you picked up)
   - Story flags (did you open the door? did the alarm go off?)
   - Roll log (what you rolled, so you can check it)
   If it is not in state, the game forgets it on the next action. That is the most common beginner bug, and the dashboard exists to catch it.

9. **Show the result on screen**
   Show, in this order so it is checkable: what you tried, what you rolled, your modifier, your total, the DC, and the outcome.
   If a player cannot see those six things, they cannot trust the roll — and neither can a tester.

10. **Loop**
    Back to step 1, until the mission ends (win, lose, or retreat) or the player quits.
    A game is mostly this loop, repeated. Missions, levels, and stories are just different actions and effects plugged into the same loop.

### Data flow, as boxes

```
[ Screen / Buttons ] -- choice --> [ Check picker ] -- check type -->
[ Dice roller ] -- roll --> [ Modifier + DC compare ] -- outcome -->
[ Effect ] -- changes --> [ Game state ] -- display --> [ Screen / Log ]
```

Every arrow is one handoff. If a step is skipped, the next step gets bad data. When something looks wrong in testing, walk the arrows backwards: was the state wrong, the DC wrong, the modifier wrong, or the roll wrong?

### What is NOT in v1 data flow

- No server, no internet, no login, no saving to the cloud
- No AI deciding rolls or writing the story on the fly
- No other players, no shop, no random paid items
- No 3D, no animation engine — text and simple numbers first

Those are later decisions, not missing pieces of v1. If a new idea needs a new box in the diagram above, it is scope growth, and it needs Tee's approval first.

---

## 3. How the game is played — in plain words

You play one person trying to get a job done in a rough, broken future. It is just you, solo. No team online, no one else playing against you.

**How a turn works:** The game tells you where you are and what is in front of you. You pick what to do — search, talk, sneak, shoot, fix something. The game rolls a 20-sided die, adds how good you are at that thing, and checks it against how hard the thing is. Then it tells you plainly what happened, and you pick the next move.

**Your main objective:** Finish the job and get out alive. For the first short mission, that means one clear job, not five at once — for example, search a wreck and bring the salvage back. If you finish the job and make it out, you win the run.

**How you lose:** If your health runs out, or the job falls apart beyond fixing, the run ends. You can try again — the dice will fall differently next time.

**Side goals, not required to win:** Find useful supplies, keep your health and gear in decent shape, and do not waste everything on the first fight. They make the next run easier, but they are not the win itself.

**What the dice are for:** They are luck plus skill. A good character still can roll badly, and a weak character still can roll well. That is the point — you make smart choices, the dice decide how well they land.

You do not need to learn rules first. Every result shows what you tried, what you rolled, your bonus, the target number, and whether it worked.

---

## Next step, when Tee says go

ACI-001: dice engine only, using the flow above, in a single offline file Tee can open on his laptop and tinker with.

On hold Oct 28 evening — Tee said no ACI tonight, he's working on the board.

Until then, this file is the dashboard. Update the Status column as pieces move, and do not mark anything "done" until Tee or Cole has actually tested it.
