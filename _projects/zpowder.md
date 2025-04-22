---
name: ZPowder
type: Game Simulation

# Listing settings

font_awesome_icon: fa-cogs

one_liner: Powder game implementation using a similar technique used by Noita.

# Project Page

source_code_url: https://gitlab.com/lucasmontec/zpowder
source_code_phrase: The source code is avaliable at GitLab.

---

## Why

This project came to be because I always loved that old cellular automata web game... https://dan-ball.jp/en/javagame/dust/

That amazed me when I was very young. It was so rich in emergent behavior that I spend way too much time tinkering with it.

Now older, I caught my self watching this view randomly some other day: https://www.youtube.com/watch?v=Ggxt06qSAe4
And the simplicity of the implementation made me absurdly curious to make my own!

But now, as a more senior Unity dev I wanted a challenge and I wanted to add my own flair to this, so that I could learn something from it.
While researching to see what was out there, I found this amazing video about Noita and their way of simulating a huge powder game world:
https://www.youtube.com/watch?v=prXuyMCgbTc

That was it! Fuel for my fire.

## What is it

So, this project is basically powder game, but implemented to run very fast on the CPU using staggered multi-threaded updating with memory aligned data.
I wanted to run a big simulation chunk with many pixels, as well as displaying them pretty. I could add chunk loading and movement in the future, but my focus was to first
simulate and run a BIG chunk really well.

I also made it so I could add more particle types easily while keeping them fast and memory efficient.

## See it!

Overview:
https://www.youtube.com/watch?v=nj7GUoX-N3Q

Gunpowder implementation with fire:
https://www.youtube.com/watch?v=UTuRFAgmswY

Stone maze with interaction between oil, gasoline and gunpowder (all on fire):
https://www.youtube.com/watch?v=SZFASBCTrLs

Water shading and physics, sand, oil, gundpowder, fire, steam, density tower:
https://www.youtube.com/watch?v=Kt9juEbSQZM

Particle states, lightning and conductivity (electricity):
https://www.youtube.com/watch?v=zGguzLiQZ20

Laser, lightning, steam + rain formation, steam formation from fire and water:
https://www.youtube.com/watch?v=OOG2PUR8bdI

Electricity igniting stuff and playing around:
https://www.youtube.com/watch?v=5pFEt_NKYNU

