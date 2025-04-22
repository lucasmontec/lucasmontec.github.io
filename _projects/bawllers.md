---

name: Bawllers
type: Game
featured: true

font_awesome_icon: fa-users

bg_video: https://www.youtube.com/embed/Krqz8MaeOC4
main_image: assets/images/bawllers.png

one_liner: A comedic action-packed combat game.

description: |
    Bawllers is a comedic fast-paced action ball combat game. Heavily inspired by Mario Kart, Smash Bros, Golf with Friends and even Team Fortress 2, it is a fun oriented game!

order: 0

---

### What is Bawllers

Bawllers is a fast-paced, multiplayer combat game where players control balls that fight using power-ups scattered throughout the level. These power-ups grant combat abilities that players use to destroy their opponents.
The game features multiple game modes, but the core objective is usually simple: the last player or team standing wins.

Abilities and pickups include: 
    * Primaries: Core combat abilities that deal damage or knock players away.
    * Mega Primaries: Overpowered combat abilities that often destroy large parts of the level and can even harm the user.
    * Secondaries: Movement-focused abilities that boost speed, jump height, or grant temporary flight.
    * Health pickups: Restore health and increase survivability.

Players can also interact with the environment, opening up different strategies and emergent gameplay depending on the mode or level.

### Tech stuff

I'm developing this game solo, as a way to learn how to finish a full project within a defined scope.

The game uses a hybrid authority model. Because of the physics-based player controller, positional authority is client-side—by design. While I could have implemented server-side simulation with client-side smoothing, I considered it out of scope for this project. Prioritizing player experience and development speed, I built a custom netcode that favors responsiveness.

To address cheating, I implemented a server-side collision arbiter that verifies each collision using buffered player states and compares them against client-reported data.
While position is client-authoritative, all other data—such as damage, abilities, and health—are server-authoritative. This shared authority approach gives me control over critical gameplay elements while keeping development agile.
The project is currently closed source, as I intend to publish the game on Steam.

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
