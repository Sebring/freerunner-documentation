---
sidebar_position: 1
---
# Installation
Freerunner is a npm package written in Typescript.

Running a npm based game is little more complicated than just including a script in the header of an html-file.
You'll need to have node installed and basic understanding of npm/yarn and obviously Javascript.

We will run a bundler that compiles and bundles our game as well as serve it through a webserver. Using node this is easy-peasy, but we will need to do some setup ([skip](quickstart)).

## Getting Started

Get started by **creating a new game**.

```shell
mkdir mygame
cd mygame
```

### Install

```
yarn add freerunner
```

### Initialize
Create `src/game.ts`

```
mkdir src
code .
```

lets create 
```typescript title=game.ts
import Freerunner from 'freerunner'
const F = Freerunner() // F is you new Crafty object
F.init()
F.e('2D, Color').attr({x:10, y:10, h:20, w:20}).color('hotpink')
```