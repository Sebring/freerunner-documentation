---
id: "FGame"
title: "Interface: FGame"
sidebar_label: "FGame"
sidebar_position: 0
custom_edit_url: null
---

## Callable

### FGame

▸ **FGame**(`selector`): [`Entity`](Entity)[]

#### Parameters

| Name | Type |
| :------ | :------ |
| `selector` | `string` |

#### Returns

[`Entity`](Entity)[]

#### Defined in

[freerunner.ts:30](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L30)

## Properties

### fps

• **fps**: `number`

#### Defined in

[freerunner.ts:43](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L43)

___

### math

• **math**: `Math`

#### Defined in

[freerunner.ts:95](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L95)

___

### rectManager

• **rectManager**: `any`

#### Defined in

[freerunner.ts:93](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L93)

___

### viewport

• **viewport**: [`Viewport`](Viewport)

#### Defined in

[freerunner.ts:96](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L96)

## Methods

### UID

▸ **UID**(): `any`

#### Returns

`any`

#### Defined in

[freerunner.ts:94](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L94)

___

### background

▸ **background**(`color`): [`FGame`](FGame)

Set background color to html color name.

#### Parameters

| Name | Type |
| :------ | :------ |
| `color` | `string` |

#### Returns

[`FGame`](FGame)

#### Defined in

[freerunner.ts:49](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L49)

___

### c

▸ **c**<`T`\>(`name`, `component`): `T`

Create a component.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends [`Component`](Component) |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `name` | `string` | name of the new component |
| `component` | `T` | component object data |

#### Returns

`T`

#### Defined in

[freerunner.ts:36](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L36)

___

### cc

▸ **cc**<`T`\>(`component`): `T`

Create a component.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends [`CComponent`](CComponent) |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `component` | [`CComponent`](CComponent) | componenent object data |

#### Returns

`T`

#### Defined in

[freerunner.ts:41](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L41)

___

### e

▸ **e**<`T`\>(`components`): `T`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends [`Entity`](Entity)<`T`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `components` | `string` |

#### Returns

`T`

#### Defined in

[freerunner.ts:42](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L42)

___

### init

▸ **init**(`width?`, `height?`, `element?`): [`FGame`](FGame)

#### Parameters

| Name | Type |
| :------ | :------ |
| `width?` | `number` |
| `height?` | `number` |
| `element?` | ``null`` \| `string` \| `HTMLElement` |

#### Returns

[`FGame`](FGame)

#### Defined in

[freerunner.ts:44](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L44)

___

### isPaused

▸ **isPaused**(): `boolean`

#### Returns

`boolean`

#### Defined in

[freerunner.ts:86](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L86)

___

### loadPlugin

▸ **loadPlugin**(`plugin`): [`FPlugin`](FPlugin)

#### Parameters

| Name | Type |
| :------ | :------ |
| `plugin` | [`FPlugin`](FPlugin) |

#### Returns

[`FPlugin`](FPlugin)

#### Defined in

[freerunner.ts:97](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L97)

___

### pause

▸ **pause**(`toggle?`): [`FGame`](FGame)

Pauses the game by stopping the `UpdateFrame` event from firing. If the game is already paused it is unpaused.
You can pass a boolean parameter if you want to pause or unpause no matter what the current state is.
Modern browsers pauses the game when the page is not visible to the user. If you want the Pause event
to be triggered when that happens you can enable autoPause in `Crafty.settings`.

#### Parameters

| Name | Type |
| :------ | :------ |
| `toggle?` | `boolean` |

#### Returns

[`FGame`](FGame)

#### Defined in

[freerunner.ts:57](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L57)

___

### s

▸ **s**<`T`\>(`name`, `template?`): `T`

Registers a system.

_Triggers Events_
- `"SystemLoaded", this` - When the system has initialized itself
- `"SystemDestroyed", this` - Right before the system is destroyed

Objects which handle entities might want to subscribe to the event system without being entities themselves.
When you declare a system with a template object, all the methods and properties of that template are copied to a new object.
This new system will automatically have the following event related methods, which function like those of components:
`.bind()`, `unbind()`, `trigger()`, `one()`, `uniqueBind()`, `destroy()`.
Much like components, you can also provide `init()` and `remove()` methods,
a `properties` dictionary which will be used to define properties with Object.defineProperty,
as well as an `events` parameter for automatically binding to events.

**`note`** The `init()` method is for setting up the internal state of the system,
if you create entities in it that then reference the system, that'll create an infinite loop.

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `name` | `string` |
| `template?` | `T` |

#### Returns

`T`

#### Defined in

[freerunner.ts:77](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L77)

___

### stop

▸ **stop**(`clearState?`): [`FGame`](FGame)

Stops the `UpdateFrame` interval and removes the stage element.

To restart, use `Crafty.init()`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `clearState?` | `boolean` | if true the stage and all game state is cleared. |

#### Returns

[`FGame`](FGame)

#### Defined in

[freerunner.ts:84](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L84)

___

### trigger

▸ **trigger**(`event`, `data`): `void`

Trigger event

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `event` | `string` | name of event |
| `data` | `any` | data to pass |

#### Returns

`void`

#### Defined in

[freerunner.ts:92](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L92)
