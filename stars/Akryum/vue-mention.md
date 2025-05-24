---
project: vue-mention
stars: 553
description: Mention component for Vue.js
url: https://github.com/Akryum/vue-mention
---

vue-mention
===========

Mention popper for input and textarea

Documentation

Vue 3 support
-------------

Install the v2 for Vue 3 support:

```
pnpm i vue-mention@next
```

You also need to install `floating-vue`:

```
pnpm i floating-vue
```

And add the default `floating-vue` styles:

import 'floating-vue/dist/style.css'

floating-vue 1 (Vue 2)
----------------------

Install the special version for floating-vue v1 (for Vue 2) support:

```
pnpm i vue-mention@1.0.0-floating-vue1
```

**⚠️ Use the exact version range `1.0.0-floating-vue1` otherwise you'll install `v1.1.0` which is for v-tooltip 2.**

You also need to install `floating-vue` v1:

```
pnpm i floating-vue@vue2
```

And add the default `floating-vue` styles:

import 'floating-vue/dist/style.css'

Sponsors
--------

Quick start
-----------

<script\>
import { Mentionable } from 'vue-mention'
const users \= \[
  {
    value: 'akryum',
    firstName: 'Guillaume',
  },
  {
    value: 'posva',
    firstName: 'Eduardo',
  },
  {
    value: 'atinux',
    firstName: 'Sébastien',
  },
\]
const issues \= \[
  {
    value: 123,
    label: 'Error with foo bar',
    searchText: 'foo bar'
  },
  {
    value: 42,
    label: 'Cannot read line',
    searchText: 'foo bar line'
  },
  {
    value: 77,
    label: 'I have a feature suggestion',
    searchText: 'feature'
  }
\]
export default {
  components: {
    Mentionable,
  },
  data () {
    return {
      text: '',
      items: \[\],
    }
  },
  methods: {
    onOpen (key) {
      this.items \= key \=== '@' ? users : issues
    },
  },
}
</script\>

<template\>
  <Mentionable
    :keys\="\['@', '#'\]"
    :items\="items"
    offset\="6"
    insert-space
    @open\="onOpen"
  >
    <textarea
      v-model\="text"
    />

    <template #no-result\>
      <div class\="dim"\>
        No result
      </div\>
    </template\>

    <template #item-@="{ item }"\>
      <div class\="user"\>
        {{ item.value }}
        <span class\="dim"\>
          ({{ item.firstName }})
        </span\>
      </div\>
    </template\>

    <template #item-#="{ item }"\>
      <div class\="issue"\>
        <span class\="number"\>
          #{{ item.value }}
        </span\>
        <span class\="dim"\>
          {{ item.label }}
        </span\>
      </div\>
    </template\>
  </Mentionable\>
</template\>
