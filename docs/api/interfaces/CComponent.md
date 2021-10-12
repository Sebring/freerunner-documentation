---
id: "CComponent"
title: "Interface: CComponent"
sidebar_label: "CComponent"
sidebar_position: 0
custom_edit_url: null
---

Same as [Component](Component) except name-attribute is required.

This gives the possibility to export component objects and create them without the need of
providing name as separate parameter.

```typescript
import MyComponent from '/components/MyComponent'

const F = Freerunner()
F.cc(MyComponent)
```

## Hierarchy

- [`Component`](Component)

  ↳ **`CComponent`**

## Properties

### events

• `Optional` **events**: `object`

#### Inherited from

[Component](Component).[events](Component#events)

#### Defined in

[freerunner.ts:104](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L104)

___

### name

• **name**: `string`

#### Defined in

[freerunner.ts:128](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L128)

___

### properties

• `Optional` **properties**: `any`

#### Inherited from

[Component](Component).[properties](Component#properties)

#### Defined in

[freerunner.ts:103](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L103)

___

### required

• `Optional` **required**: `string`

#### Inherited from

[Component](Component).[required](Component#required)

#### Defined in

[freerunner.ts:102](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L102)

## Methods

### init

▸ `Optional` **init**(): `void`

#### Returns

`void`

#### Inherited from

[Component](Component).[init](Component#init)

#### Defined in

[freerunner.ts:101](https://github.com/Sebring/freerunner/blob/eaa5ade/src/freerunner.ts#L101)
