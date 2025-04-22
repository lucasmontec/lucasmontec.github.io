---
name: Plants
type: Experiment

#Added to override the project page
direct_link: https://gitlab.com/lucasmontec/plantmovementtechniquesonunity

main_image: /assets/images/plants.png

one_liner: Playing with Verlet rope simulations and interacting with Physx.
description: |
    This is a simple experiment I did exploring verlet rope simulation playing along with Unity's native Physics engine.
---

This is another dive into simulating some natural behavior with Verlet integration. This one simulates plants and also interact with Unity's Physics.

```
Bones are used to bend a skinned mesh.
No physics engine was used.
Each bone position is calculated based on a Verlet simulation with a bit of gravity and an elastic force toward the plant's original position.
Particles are kept together with a distance constraint simulation.
Pushing is just another distance constraint.
```

Here's a video showing it:

https://www.youtube.com/watch?v=-FRD-U4_O3Q
