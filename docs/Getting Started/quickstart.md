# Quickstart

If you already know how to install using npm/yarn and how to get typescript bundled and served - lets get some game code running! 

## Getting Started

Get started by **creating a new game**.

```shell
mkdir mygame
cd mygame
npm init -y
```

### Install

```
npm i freerunner
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