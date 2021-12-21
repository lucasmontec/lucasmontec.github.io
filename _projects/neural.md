---
name: NeuralNet with scalaJS
type: Game

bg: /assets/images/neural.png

#Added to override the project page
direct_link: https://lucasmontec.github.io/scala-neural-net-test/

main_image: /assets/images/neural.png

one_liner: A fun experiment to play with scala and neural networks.
description: |
    I love artificial inteligence. This was my first attempt at this exciting concept that are neural networks. I took advantage to code this in scala since I find this language's paradigm quite amusing.
---

I love artificial inteligence. This was my first attempt at this exciting concept that are neural networks. I took advantage to code this in scala since I find this language's paradigm quite amusing.

This example consists of 'insect' like creatures with a steering movement behaviour that is controlled by a neural network. Each creature has its own network that is initialized with random values.

The creatures are represented by a circle with a line to indicate the creature orientation. The line is the creature 'face'. Also, there are purple squares in this simulation. Those are creature food.

As time passes, each generation ends. When a generation of creatures end, the algorithm selects the best creatures and breeds them to create the new generation. The best creatures are the ones that ate more food during the generation. Just selecting the best is not enough though, the algorithm also applies random mutations to the sons of the new generation, ensuring that new behaviour is always possible.

Each creature is bred by combining its genes. A creature gene is one of its weights in the network, the combination choses one of the parents genes and has a change of mutating it.

There is more to it than this, but I started this project a long time ago and I'm writing about it some years later.