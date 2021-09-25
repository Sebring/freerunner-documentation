# Entities and Components

_The core of a Freerunner game is it's collection of components._


During development you will create lots of _components_ that defines special attributes or behaviours.
Keep the components small and grow complexity by combining components.
These components will make our _entities_ come alive and have them being rendered, collieded with or even killed by depending on our game genre.

The most basic components are `2D` that defines position `{x, y}` and size `{h, w}` and `Color` that will fill a `2D` with a solid color.

Let's say we want a brown box in our game represented as a brown square to keep sprites out of the example.

```typescript
let brownBox = F.e('Box') // e for entity

brownBox.addComponent('2D')
brownBox.addComponent('Color')

brownBox.attr({ x:10, y:10, h:20, w:20 })
brownBox.color('brown')
```

Easy to follow, right? But lots of code such a simple game object. Let's create a more generic component for our box.

```typescript
F.c('Box') // c for component
  .addComponent('2D, Color')  // this time we chain
  .attr(({ x:10, y:10, h:20, w:20 }))
  .color('brown')

let brownBox = F.e('BrownBox, Box') // e for.. you know by now
// another one, but red
let redBox = F.e('RedBox, Box').color('red')
```
:::info
If you try this code you will also need to add the component 'DOM' or 'Canvas' to actually have it rendered.
:::

While the above code was valid, below is an _dreamcode_ example of how powerful the component entity pattern is.
```typescript
F.c('Plumber')
    .addComponent('Jumper, Collector, Stomper')
    .speed(200)
F.c('HedgeHog')
    .addComponent('Jumper, Collector, Spinner')
    .speed(500)

let player1 = F.e('Mario, Plumber')
    .addComponent('Controllable').controller(1)
let player2 = F.e('Sonic, Hedgehog')
    .addComponent('Controllable').controller(2)
let player3 = F.e('Luigi, Plumber')
    .addComponent('Controllable').controller(3)

for (let i; i<10; i++) {
    F.e('Goombas, Stompable, Spinnable, RandomSpawnPos')
    F.e('Star, Collectable, RandomSpawnPos')
}
```
Read more on entities and components.

Communication is event-driven. A component might listen to a 'move'-event, check for collisions and then fire a 'collide'-event on the other component. This way components can be self-sustained we ensure low coupling.