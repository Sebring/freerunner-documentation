---
sidebar_position: 1
title: "Intutive API"
---

# Intutive API
_Average time spent in the garage is 10% tinkering, 10% thinking and 80% looking for the tool you used just a second ago._

## Limited API exposure
_The API will grow as your game does_  
Thanks to the <abbr title="entity component system">ECS</abbr> the API will grow as your game evoleves.
You won't see any sprite related functions on you entities until you add the sprite-component, you can't even set velocity unless you have added a component that enables it.

## Evolving API
_You define the API to suit your needs_  
As you create components you are also creating the API.
Tired of calculating `x` and `y` for placement in a 16 pixel grid? Define a grid component with grid size and add a `gridPlace` function.

```javascript
// basic 2D
ball.x = 64
ball.y = 512

// using "grid component"
ball.addComponent('Grid').grid(16)
ball.gridPlace(4, 32)
```

## Event driven communication
Communication is event driven. You can trigger events on a specific entity, a set of components or globally.
All entities and components can trigger and bind to events, as well as the Freerunner instance for global events.
You will add a lot of complex features just creating different components that `bind` and `trigger` different events.  
(link to event guide)


----

```javascript
player1.bind('Explode', (data) => {
    this.hp -= data.damage
    this.vy += power
})

// global
F.trigger('Explode', { damage: 19, power: 34 })

// component
bomb.bind('CollideWithPlayer', (player) => {
    if (this._hasExploded) return
    player.trigger('Explode', { damage: 22, power: 42 })
    this._hasExploded = true
})
```