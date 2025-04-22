---

name: Bawllers
type: Game
featured: true

font_awesome_icon: fa-users

bg_video: https://www.youtube.com/watch?v=Krqz8MaeOC4
main_image: assets/images/bawllers.png

one_liner: A comedic action-packed combat game.

description: |
    Bawllers is a comedic fast-paced action ball combat game. Heavily inspired by Mario Kart, Smash Bros, Golf with Friends and even Team Fortress 2, it is a fun oriented game!

order: 0

---

### What is Bawllers

Bawllers is a fun fast paced multiplayer combat game. It's a ball fighting game where players get combat abilities from power ups around the levels, then use those abilities to destroy the other players.
The game has several game modes but usually the last standing player or team wins!

The game has several abilities and pickups: 
    * Primaries focus on combat, damaging players or pushing them away.
    * Mega primaries focus on ultra combat: They are ultra strong primaries that usually destroy more than half of the map and can damage the casting player too.
    * Secondaries focus on player movement, allowing players to move faster, jump higher or even fly for a bit.
    * Health pickups: recover player damage, allow for surviving longer.

The players can interact with the level too, providing several gameplay alternatives for different game modes or emergent behavior within a run of the same level.

### Tech stuff

I'm developing this game on my own to learn how to finish a project and deal with a fixed scope!

The game is hybrid authority. Because of the physics-based player controller, the player position authority is client-side. This was intentional. I could spend time implementing a server simulated authority,
with some slack for the client to feel fast and smooth, but I deemed this to be out of scope. Instead, I designed my netcode to favor the player experience and development velocity. This allowed me to create this game much faster.
To cope with cheating, I added a collision arbiter that checks server side behavior for players in each collision, simulating their buffered positions and cross checking with client reported data.
Still, the focus is to create a fun complete game fast, and on my own. It's shared authority becase other player data like damage, abilities and such, are all server authoritative. This allows me to still have some control over what
is happening and deal a little bit with cheating.

For now, this is closed source as I intend to publish the game on Steam.

### Closed alpha playtest videos

#### Version: Blue Cheese

<div class="video-container">
    <iframe class="video" src="https://www.youtube.com/watch?v=nt9QncL-Cd8" frameborder="0" allowfullscreen></iframe>
</div>
<p></p>

#### Version: Stomp and Brake

<div class="video-container">
    <iframe class="video" src="https://www.youtube.com/watch?v=Krqz8MaeOC4" frameborder="0" allowfullscreen></iframe>
</div>
<p></p>

#### Version: Old pre-alpha level design

<div class="video-container">
    <iframe class="video" src="https://www.youtube.com/watch?v=c8CTHWjEq7w4" frameborder="0" allowfullscreen></iframe>
</div>
<p></p>

#### Version: Macross

<div class="video-container">
    <iframe class="video" src="https://www.youtube.com/watch?v=tnz6hXff5dA" frameborder="0" allowfullscreen></iframe>
</div>
<p></p>
