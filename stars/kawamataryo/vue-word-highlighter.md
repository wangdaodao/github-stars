---
project: vue-word-highlighter
stars: 325
description: The word highlighter library for Vue 2 and Vue 3.
url: https://github.com/kawamataryo/vue-word-highlighter
---

The word highlighter library for Vue 2 & Vue 3.

### Demo

### CodeSandbox

📦 Installation
---------------

### Vue 3

yarn add vue-word-highlighter
# or
npm install vue-word-highlighter

### Vue 2

powered by vue-demi.

yarn add vue-word-highlighter @vue/composition-api
# or
npm install vue-word-highlighter @vue/composition-api

If you get a `Uncaught TypeError: e.defineComponent is not a function` error, and it doesn't work, try this one from vue-demi

🚀 Usage
--------

To use it, just provide it with search words to props and a body of text to default slots.

<template\>
  <WordHighlighter query\="vue"\>
    The word highlighter library for Vue 2.x Vue 3.x 💅
  </WordHighlighter\>
  <!--  or
  <WordHighlighter 
    query="vue"
    textToHighlight="The word highlighter library for Vue 2.x Vue 3.x 💅"
  />
  \-->
</template\>

<script lang="ts">
import { defineComponent } from "vue";
import WordHighlighter from "vue-word-highlighter";
export default defineComponent({
  name: "App",
  components: {
    WordHighlighter,
  },
  setup() {
    return {};
  },
});
</script\>

Output.

⚒ Details
---------

### Props

Property

Type

Required?

Description

query

String or RegExp

✓

Search words. Can be use string or regular expressions.

caseSensitive

Boolean

Whether string being searched is case sensitive. defaults to `false`.

diacriticsSensitive

Boolean

Whether string being searched is diacritics sensitive. defaults to `false`.

splitBySpace

Boolean

Whether split the string with spaces to make it a search string. If false, the string is being searched as a whole word. defaults to `false`. When the query is set to a RegExp, the value of splitBySpace will be set to false.

matchMode

"partial" or "exact"

If "exact", only whole words are matched. For example, searching for "Java" excludes "JavaScript". Defaults to "partial".

highlightTag

String

Type of tag to wrap around highlighted matches; defaults to `mark`.

highlightClass

String or Object or Array

Classes to be added to highlighted tag. Similar to class bindings in vue, it accepts Array syntax, Object syntax, or class as String.

highlightStyle

String or Object or Array

Styles to be applied to highlighted tag. Similar to style bindings in vue, it accepts Array syntax, Object syntax, or plain styling as String.

wrapperTag

String

Type of tag to wrap around whole text; defaults to `span`.

wrapperClass

String or Object or Array

Classes to be added to wrap around the whole tag. Similar to class bindings in vue, it accepts Array syntax, Object syntax, or class as String.

textToHighlight

String

Text to be highlight. If this is not specified, the default slot value will be used for the search.

htmlToHighlight

String

HTML to be highlighted。This value is inserted as `InnerHTML`. This props takes precedence over `textToHighlight` and `slot`. This props is an experimental feature that only works for Vue3.

### Emits

Property

Type

Description

matches

Array

Returns matches words. This event fires when mounted and when the query and highlighted text are changed.

By using matches emit, you can know from the parent component whether it is highlighted by VueWordHighlighter or not.

Example

<template\>
  <div\>
    Matched word count: {{ matches.length }}
  </div\>
  <WordHighlighter query\="vue" @matches\="(e) => { matches = e }"\>
    The word highlighter library for Vue 2.x Vue 3.x 💅
  </WordHighlighter\>
</template\>

<script lang="ts">
import { defineComponent, ref } from "vue";
import WordHighlighter from "vue-word-highlighter";
export default defineComponent({
  name: "App",
  components: {
    WordHighlighter,
  },
  setup() {
    const matches \= ref(\[\]);
    return {
      matches
    };
  },
});
</script\>

📄 License
----------

vue-word-highlighter is available under the MIT License.
