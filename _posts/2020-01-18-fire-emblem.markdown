---
layout: post
title:  "Fire Emblem: The Sacred Stones"
date:   2020-01-18 12:06 +0100
categories: gameplay bot AI
---
Recently I had a surge of inspiration to start working on a game playing machine learning project. The game I thought about learning is Fire Emblem: The Sacred Stones, probably out of nostalgia. The idea to do a combination of game development and artificial intelligence comes up every so often, but maybe this is the one to stick around.

What made similar projects fail in the past was attempting too much at once, which is why I am now planning on starting small and expanding ever so slightly when I am at a comfortable point in development. I'll also try to not over-engineer this project too much (though I probably will..)

I have done some preliminary research and came across [this webpage][fe-calculations], where all sorts of damage, accuracy metrics are listed in a comprehensive format. This will prove useful in designing a custom environment to play a basic version of the game in.

I have not yet decided where to go for developing this game and see a few potential avenues to take:
- `Python`: python is easy for quick-and-dirty development, drawing the game would not be the most attractive nor fastest to implement, but the speed of development might make this a good choice.
- `Unity`: I have done some very basic things in Unity3D, and I suspect that Unity2D would be very helpful to create the game layout. It is however not the primary goal to make a playable Fire Emblem: Sacre Stones clone, rather to have the core logic implemented and having a bot learn how to play it efficiently.
- `SFML`: I have previously dabbled with SFML for 2D game development, but it is probably overkill to do everything from scratch. Speed would be a plus, though, as a bot using tensorflow (haven't decided on this either) would work better in C++ or python than in Unity (unless I am unaware of a link between Unity and Tensorflow).

There are many different aspects of the game that have to be implemented:
- Movement
- Basic Combat (Damage calculations)
- Advanced Combat (Weapon skills, Terrain influence)
- Different items that can be used
- Unlockable doors
- Interactions between units (Support, Trade)
- Shops
- Supply convoy usage
- Recruitable enemies/neutrals
- Optional objectives
- Breakable walls
- Healing from standing on specific tiles
- Carefully planing weapon skill (Only 1 S-rank allowed!)

This is far to much to design a model for from the get-go. Instead the first attempt of this project will only keep into account `Movement` and `Basic combat`. This should prove a sufficiently large challenge to model as a start. A baseline level that any model should be capable of clearing is the first floor of the `Tower of Valni` with a couple of high-level units.

[fe-calculations]: https://serenesforest.net/the-sacred-stones/miscellaneous/calculations/