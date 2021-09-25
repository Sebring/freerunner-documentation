---
sidebar_position: 1
---

# Introduction
_Power is nothing without control._

Freerunner aims to be easy for the developer, yet provide full power and total control.
 
## Goals of Freerunner
**Intutive API**  
- Learn faster
- Remember better

**Scale well**  
- Keep performance as games grows
- Keep overview of project as it grows
- Entity component system with modules

**Great documentation**  
- Relevant, mobile friendly and filled with inspiring examples.

:::note
Freerunner was created by the love for the game engine [Crafty](http://craftyjs.com), the must-read book [game-programmings-patterns](https://gameprogrammingpatterns.com) as well as my <strike>obsession</strike> interest for parkour.
:::

## Overview
Freerunner is written in Typescript, giving you the power of intellisense and typed objects.
Feel free to write you own parts in Javascript, you will still benefit from the intellisense.
To develop a Freerunner game it needs a web application bundler and it comes configured for parcel.
[Read more](link)

### Intutive API
_Event driven component entity system_.

#### Components and entities
You build up complexity by adding new components to your entities, not by adding more code to the entity itself. 

Being able to move might be a component that adds velocity and update position each frame, responding to input another and being able jump a third. This is easy on the brain not only during development but also when bug-hunting.
Components should be small and add related attributes and behaviours.

:::info
Turns out the cpu thinks this is great too, it tends to cache well and reduce cache misses thanks to data-locallity. [Read more](https://gameprogrammingpatterns.com/data-locality.html).
:::

#### Event driven communication
The engine, components, entities and systems communicates through events. They can trigger events as well as acting on them. This keeps them de-coupled and independent of each other. 

Example:  
When the player collides with a floor sensor it triggers an event which a door listen to this and opens, however we also had a spike trap that activates when this event is triggered.

### Scaling Projects
_How do you want your game served, all you can eat buffet or a huge bowl of spaghetti?_

A game should scale well, not only performance wise but also for your own sanity.
Ever turned away from a project a few weeks only to see that what you once thought was a structured project has transformed into mess?
Yeah, me too, too many times.
Fool me once...

#### Solid components and modules
By creating small independent components and having them separated physically in different files your game won't grow into a pile of spaghetti.
I think a file shouldn't be much longer than 300 lines of code.
Same as keeping components do one thing good same goes for your files.

If there is a bug relating to collecting a star it should be easily found in `/components/starCollector.ts` or maybe `/components/Collectable.ts` and not hide in some nested if-statement related to player input and collision in `./lookMa-MyGameInOnefile.js`.

:::info
Turns out our bundler thinks this is great too, having structured your code as modules it can tree shake modules never imported. [Read more](https://developers.google.com/web/fundamentals/performance/optimizing-javascript/tree-shaking/).
:::

### Amazing documentation
_In the workshop I spend 5% of my time thinking on what to do, 15% tinkering on my project and 80% looking for the tool I was just using._ 

Amazing documentation will reduce the learning curve and set the pace of development. Amazing documentation will show up front what you can expect from selecting Freerunner as the engine of your game, no need to spend hours in getting to know the engine just to find out you are not happy with the developemnt environment.

Who knows, maybe this amazing documentation is why you choose this engine over another.
