---
slug: frerunner-0-0-1
title: Freerunner 0.0.1
authors: [sebring]
tags: [docusaurus]
---

# Freerunner - a modern Crafty

I've just published Freerunner 0.0.1 on npm!

It is just a raw wrapper around [crafty](http://craftyjs.com) with all its glory and also all its legacy code. Little by little I will carve and shape it to my imagination of a really simple yet powerful game engine. Will the API always be compatible with Crafty? I don't know, but as long as i makes sense, it makes sense.

## Nearest milestones:

### 0.1.0 - the package
A working npm-package with crafty wrapped with limited typescript support. Using an full featured game engine means a the api is big and the intellisense enabled by typescript is such a timesaver. Writing interfaces and definitions will be ongoing and I do not strive to make it complete yet but will add more support for each release.

### 0.2.0 - the imports
Having components as separate es modules. This will keep game code manageble as the game evolves and features are added. However it will also make reusing components even easier.

From:
```javascript
Crafty.c('MyComponent', {
    init: function() { /.../ },
    events: /../
})
```

To:
```javascript
import MyComponent from '/components/MyComponents'

Freerunner.cc(MyComponent)
```

### 0.3.0 -- the plugins
Using a plugin should be as easy as importing it and loading it into Freerunner. A plugin should be able to add
* components
* systems
* static resources as sprites and sounds

Example
```javascript

// imaginary plugin with level generator, sprits and mini-map
import DungeonPlugin from 'freerunner-dungeon'
// imaginary plugin that adds inventory support
import InventoryPlugin from 'freerunner-medivalitems'

Freerunner.addPlugin(DungeonPlugin)
Freerunner.addPlugin(InventoryPlugin)

const level1 = DungeonPlugin.generateLevel() // custom functions
```

Plugins should have a defined way of testing and showcasing them, like a minimal demo.

```bash
yarn demo
```