---
project: vue-virtual-scroll-list
stars: 4467
description: ⚡️A vue component support big amount data list with high render performance  and efficient.
url: https://github.com/tangbc/vue-virtual-scroll-list
---

Table of contents
-----------------

-   Advantages
-   Live demo
-   Simple usage
-   **Props type**
    -   Required props
    -   Optional props
    -   Public methods
-   Attentions

Advantages
----------

-   Only 3 required props, simple and very easy to use.
    
-   Big data list with high render performance and efficient.
    
-   You don't have to care about item size, it will calculate automatic.
    

Live demo
---------

https://tangbc.github.io/vue-virtual-scroll-list

https://codesandbox.io/s/live-demo-virtual-list-e1ww1

Simple usage
------------

npm install vue-virtual-scroll-list --save

Root component:

<template\>
  <div\>
    <virtual-list style\="height: 360px; overflow-y: auto;" // make list scrollable
      :data-key\="'uid'"
      :data-sources\="items"
      :data-component\="itemComponent"
    />
  </div\>
</template\>

<script\>
  import Item from './Item'
  import VirtualList from 'vue-virtual-scroll-list'
  export default {
    name: 'root',
    data () {
      return {
        itemComponent: Item,
        items: \[{uid: 'unique\_1', text: 'abc'}, {uid: 'unique\_2', text: 'xyz'}, ...\]
      }
    },
    components: { 'virtual-list': VirtualList }
  }
</script\>

Item component:

<template\>
  <div\>{{ index }} - {{ source.text }}</div\>
</template\>

<script\>
  export default {
    name: 'item-component',
    props: {
      index: { // index of current item
        type: Number
      },
      source: { // here is: {uid: 'unique\_1', text: 'abc'}
        type: Object,
        default () {
          return {}
        }
      }
    }
  }
</script\>

More usages or getting start you can refer to these clearly examples.

Props type
----------

### Required props

             **Prop**             

**Type**

**Description**

`data-key`

String|Function

The unique key get from `data-sources` in each data object. Or a function called with each `data-source` and return their unique key. Its value **must be unique** in `data-sources`, it is used for identifying item size.

`data-sources`

Array\[Object\]

The source array built for list, each array data must be an object and has an unique key get or generate for `data-key` property.

`data-component`

Component

The render item component created / declared by vue, and it will use the data object in `data-sources` as render prop and named: `source`.

### Optional props

**Commonly used**

           Prop           

Type

Default

Description

`keeps`

Number

30

How many items you are expecting the virtual list to keep rendering in the real dom.

`extra-props`

Object

{}

Extra props assign to item component that are not in `data-sources`. Notice: `index` and `source` are both occupied inner.

`estimate-size`

Number

50

The estimate size of each item, if it is closer to the average size, the scrollbar length looks more accurately. It is **recommended** to assign the average that calculate by yourself.

**Uncommonly used**

               Prop               

Type

Default

Description

`start`

Number

0

Setting scroll position stay start index.

`offset`

Number

0

Setting scroll position stay offset.

`scroll`

Event

Emited when scrolling, param `(event, range)`.

`totop`

Event

Emited when scrolled to top or left, no param.

`tobottom`

Event

Emited when scrolled to bottom or right, no param.

`resized`

Event

Emited when item resized (mounted), param `(id, size)`.

`direction`

String

vertical

Scroll direction, available values are `vertical` and `horizontal`

`page-mode`

Boolean

false

Let virtual list using global document to scroll through the list.

`top-threshold`

Number

0

The threshold to emit `totop` event, attention to multiple calls.

`bottom-threshold`

Number

0

The threshold to emit `tobottom` event, attention to multiple calls.

`root-tag`

String

div

Root element tag name.

`wrap-tag`

String

div

List wrapper element `(role=group)` tag name.

`wrap-class`

String

List wrapper element class name.

`wrap-style`

Object

{}

List wrapper element inline style.

`item-tag`

String

div

Item wrapper element `(role=item)` tag name.

`item-class`

String

Item wrapper element class name.

`item-class-add`

Function

A function that you can return extra class (String) to item wrapper element, param `(index)`.

`item-style`

Object

{}

Item wrapper element inline style.

`item-scoped-slots`

Object

{}

The `$scopedSlots` for item component.

`header-tag`

String

div

For using header slot, header slot wrapper element `(role=header)` tag name.

`header-class`

String

For using header slot, header slot wrapper element class name.

`header-style`

Object

{}

For using header slot, header slot wrapper element inline style.

`footer-tag`

String

div

For using footer slot, footer slot wrapper element `(role=footer)` tag name.

`footer-class`

String

For using footer slot, footer slot wrapper element class name.

`footer-style`

Object

{}

For using using footer slot, footer slot wrapper element inline style.

### Public methods

**Usefull public methods**

You can call these methods via `ref`:

Method

Description

`reset()`

Reset all state back to initial.

`scrollToBottom()`

Manual set scroll position to bottom.

`scrollToIndex(index)`

Manual set scroll position to a designated index.

`scrollToOffset(offset)`

Manual set scroll position to a designated offset.

`getSize(id)`

Get the designated item size by id (from `data-key` value).

`getSizes()`

Get the total number of stored (rendered) items.

`getOffset()`

Get current scroll offset.

`getClientSize()`

Get wrapper element client viewport size (width or height).

`getScrollSize()`

Get all scroll size (scrollHeight or scrollWidth).

`updatePageModeFront()`

When using page mode and virtual list root element offsetTop or offsetLeft change, you need call this method manually.

Attentions
----------

This component use an `in-place patch` strategy to render list instead of `v-for` and `:key`. This way achieves the best efficient, but only suitable when your list output does not rely on item component inner state or temporary DOM state (e.g. form input values).

But how to deal with such a situation? Without maintaining inner state, recommend to use props and dispatch (stateless component), here is an example keep-state.

Contributions
-------------

Welcome to improve this component with any issue, pull request or code review.

Changelogs
----------

Maintain and update occasionally, for changes see release.

License
-------

MIT License.
