# TAIG Hammer Game — How to Play

A plain-language manual. No gamer talk needed. If you have never played a game like this before, start here.

## What is this game?

TAIG Hammer is a short, solo game you play by yourself, on your own computer.
You are one person, in a rough, broken future, trying to get one job done and get out alive.

The job is simple:
Search a wrecked transport in the rust yards, find the salvage inside, and get out through a jammed hatch.
A raider is watching the far side of the wreck. That is the whole story for this first game.

There is no team online, no other players, no shop, no money to spend, and no account to make.
It is an original game. It is not made by, or connected to, any other game company.

## Getting the game

You get it from GitHub only. That is where the game files live.

If you do not have it yet, on your computer:
```
git clone https://github.com/the-ai-guy-2k/taig_hammer.git
```

If you already have it, and you want the newest version, go into that folder and run:
```
git pull
```

That is the only download step. There is no installer to run, no app store, and nothing to pay for.
Once you have downloaded it, you do not need the internet to play.

## Starting the game

1. Open the folder you just downloaded, called `taig_hammer`.
2. Find the file called `hammer-game-dice-v1.html`.
3. Double-click it. It will open in your web browser, like a web page.

That is it. You do not need to set up a server, type commands to play, or log in anywhere.
If you close it and open it again later, you will pick up where you left off. See "Pausing and closing" below.

## What you see on screen

At the top, you will see your job, in plain words:
"Finish the job and get out alive."

Under that, you will see your numbers, always visible:
- Health: 20 out of 20 when you start. This is how much hurt you can take. If it gets to 0, the run ends.
- Supplies: 3 when you start. Think of these as first-aid packs you can use to get health back.
- Gear condition: 100% when you start. This is how good your gear is. It goes down sometimes, but it will never end your run by itself in this game.
- Salvage: Not found, until you find it. This is the thing you came to get. You cannot finish without it.
- Raider: Watching, until you get past him or stop him. This is the person watching the wreck.

Under that, you will see buttons for what you can do. You play with your mouse, or by tapping, only. No typing, no codes.

## How a turn works

Every turn is the same simple pattern:
1. You pick what to do, by clicking a button.
2. The game rolls a 20-sided die for you. You do not roll anything yourself.
3. The game adds a small bonus, based on how good you are at that thing.
4. The game checks that total against how hard that thing is.
5. The game tells you, in plain words, what happened, and your numbers update.

You can check every roll. For every roll, the game shows you, in this order:
- What you tried
- What number you rolled
- Your bonus
- Your total
- How hard it was
- What happened

There is also a roll log underneath, so you can look back at every roll in order.

Two special rolls to know:
- If you roll a 20, that is the best possible roll. It counts as a great success, before the bonus is even added.
- If you roll a 1, that is the worst possible roll. It counts as a bad fail, before the bonus is added, and your gear goes down by 10%.

Otherwise, if your total is equal to, or higher than, how hard it was, you succeed. If it is lower, you fail.

## What you can do

There are five things you can do, every turn:

### 1. Search the wreck
You look inside the wreck for the salvage.
- You are good at this: +3 bonus.
- How hard it is: 12.
- If you succeed, you find the salvage.
- If you roll a 20, you find the salvage and you also gain 1 supply.
- If you fail, you find nothing, and you are not hurt.
- If you roll a 1, you find nothing, you lose 2 health because you cut yourself on the wreckage, and your gear goes down 10%.

### 2. Sneak past the raider
You try to get past the raider without him seeing you.
- Your bonus: +2.
- How hard it is: 14. This is the hardest one, on purpose.
- If you succeed, the raider does not see you.
- If you roll a 20, the raider does not see you, and you gain 1 supply.
- If you fail, the raider sees you, and you lose 5 health.
- If you roll a 1, the raider sees you, you lose 5 health, and your gear goes down 10%.

### 3. Shoot the raider
You try to stop the raider.
- Your bonus: +3.
- How hard it is: 13.
- If you succeed, the raider is down.
- If you roll a 20, the raider is down, you are not hurt, and you gain 1 supply.
- If you fail, you miss, and you lose 4 health because he shoots back.
- If you roll a 1, you miss, you lose 4 health, and your gear goes down 10%.

You do not have to shoot him to win. Sneaking past him works too. Pick whichever way you like.

### 4. Fix the jammed hatch and exit
This is how you get out, and how you win.
- Your bonus: +2.
- How hard it is: 11.
- Important: if you have not found the salvage yet, the game will not roll at all. It will say: "You have not got the salvage yet. Search the wreck first." That is not a fail. Just go search first, then come back.
- If you have the salvage and you succeed, you get out alive. You win.
- If you roll a 20 with the salvage, you also win.
- If you fail, the hatch stays jammed, and you lose 2 health.
- If you roll a 1, the hatch stays jammed, you lose 2 health, and your gear goes down 10%.

### 5. Use a supply
This is not a roll. It is just using one of your first-aid packs.
- It uses 1 supply.
- It gives you back 5 health, up to a maximum of 20.
- If you have 0 supplies left, the game will say: "No supplies left." Nothing else changes.

## How you win, and how you lose

You win when two things are both true:
1. You have found the salvage, AND
2. You fix the jammed hatch and get out.

When you win, you will see:
"Job done. You got out alive."

You lose when your health gets to 0. That is the only way to lose in this first game.
When you lose, you will see:
"Run over. Health out."

After a win or a loss, press "Play again" to start a fresh run. That resets everything exactly to the start: Health 20 out of 20, Supplies 3, Gear 100%, Salvage Not found, Raider Watching, and an empty roll log.

## Pausing and closing

Pausing:
- Press "Pause" at any time. The game freezes, and the other buttons lock, so you cannot accidentally make a move.
- Your progress is saved on your own computer, in your browser.
- Press "Resume" to carry on exactly where you left off, with the same health, supplies, gear, salvage, and raider state.

Closing:
- Just close the tab or window when you are done. You do not need to log out, and nothing is saved online.
- Open the same file again later, and you will pick up where you left off.

One honest limit: saved on your computer means in that browser, on that device, for that file. If you open the game in a different browser, or on a different computer, it will start fresh there. If your browser blocks saving for files opened this way, the game will still play, but closing and reopening will not remember where you were. That is a browser limit, not a different game.

## A few tips, in plain words

- Search first. You cannot leave without the salvage, so finding it early helps.
- Do not waste all your supplies at full health. A supply gives you 5 health back, but you cannot go over 20.
- Gear going down is not the end. It only goes down on a roll of 1, it never goes below 0%, and it will not end your run by itself.
- You do not have to fight the raider. Sneaking past him counts just as much as stopping him, for getting out alive.
- If you are stuck on the hatch, check your salvage line. If it still says Not found, go search again.

## If something does not work

- File will not open: make sure you are opening `hammer-game-dice-v1.html`, not the other files in the folder. That is the game file.
- Screen looks blank: try opening it in a different browser, or check that you downloaded the whole folder, not just one file.
- Your saved game is gone: did you open it in a different browser, or on a different computer? Saved progress stays in the browser you played in. Open it there again.
- A button does not work: check if the game is paused, or if the run has already ended with a win or a loss. Press "Resume" if paused, or "Play again" if the run is over.

## What this game does not do

- No internet needed after you download it.
- No account, no login, no password.
- No money, no shop, no paid extras.
- No other players, no chatting, no sharing scores.
- No sound, music, or video in this first version.
- No second mission yet. This is one short job, start to finish, on purpose.

That is the whole manual. Open the file, pick an action, and see what happens.
