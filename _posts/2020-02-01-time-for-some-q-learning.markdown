---
layout: post
title:  "Time for some Q-learning"
date:   2020-02-01 10:53 +0100
categories: ai fe-sacred-stones
---

As laid out in my previous post, I am currently in the process of recreating Fire Emblem: The Sacred Stones with the intention of training an AI to play the game.

Right now, it is possible to provide a json configuration file with level details to spin up a game instance with option for movement and basic combat. Movement is illustrated in the images below:

![General overview of the level]({{ site.url }}/assets/FE-SS-Tower-of-valni-general-image.png)
![Illustration of movement highlighting]({{ site.url }}/assets/FE-SS-Tower-of-valni-movement-image.png)

I also added the logic for the enemy AI like it is in the original game. This means enemies don't hunt you down unless you are in their attackable zone, they don't roam but stay still until provoked. The next step is to start integrating the machine learning bot into the game logic. For this we need to have a way to gather all information about the current game state for it to reason on (aka as an input vector to the NN that will estimate Q-values). A first naive idea for encoding the game state is to have for each tile the stats of the unit occupying it (+ eventual terrain stats in the future) and stats for all items in its inventory. Tiles without a unit on them would have 0 padded to keep a consistent size. This, however, does not scale well. An initial run of the relatively small level that is used for testing would have a game state of around 18120 values. I will have to look into reducing the size by handling some of the redundancy that may be present in the encoding. It might not be useful as an input to a NN but Huffman encoding can provide fixed-length encoding, maybe that is a solution I could try to pursue.