---
project: vue-virt-list
stars: 368
description: 【持续更新中】⚡️ 一个支持vue2&vue3的高性能虚拟(滚动)列表组件 👉🏻 轻量5KB 百万数据渲染 满帧率滚动 丰富场景支持  📑 [vue虚拟列表] [vue虚拟滚动列表][vue虚拟树] [vue-virtual-list] [vue-virtual-scroll-list] [vue-virtual-scroller] [vue-virt-tree] 
url: https://github.com/kolarorz/vue-virt-list
---

vue-virt-list 虚拟列表 虚拟滚动列表 虚拟树
=============================

Documentation
-------------

To check out docs, visit vue-virt-list

👉 Advantages

Quick Start
-----------

npm install vue-virt-list -S

### Options API

<template\>
  <div style\="width: 500px; height: 400px"\>
    <VirtList itemKey\="id" :list\="list" :minSize\="20"\>
      <template #default\="{ itemData, index }"\>
        <div\>{{ index }} - {{ itemData.id }} - {{ itemData.text }}</div\>
      </template\>
    </VirtList\>
  </div\>
</template\>

<script\>
  import { VirtList } from 'vue-virt-list';
  export default {
    components: { VirtList },
    data() {
      return {
        list: \[{ id: 0, text: 'text' }\],
      };
    },
  };
</script\>

### Composition API

<template\>
  <div style\="width: 500px; height: 400px"\>
    <VirtList itemKey\="id" :list\="list" :minSize\="20"\>
      <template #default\="{ itemData, index }"\>
        <div\>{{ index }} - {{ itemData.id }} - {{ itemData.text }}</div\>
      </template\>
    </VirtList\>
  </div\>
</template\>

<script setup lang\="ts"\>
  import { ref, shallowRef } from 'vue';
  import { VirtList } from 'vue-virt-list';
  const list \= ref(\[{ id: 0, text: 'text' }\]);

  // 大数据建议使用 shallowRef: https://kolarorz.github.io/vue-virt-list/guide/instructions#shallowref
  // const list = shallowRef(\[{ id: 0, text: 'text' }\])
</script\>

WeChat
------

有问题可扫码加好友进入技术交流群（备注github账号名&vue-virt-list）

Sponsor
-------

开源不易，如果帮助到你，请作者喝杯咖啡吧~

### 感谢您的慷慨

-   AliPay
    
    -   \*\*丹
    -   \*\*平
    -   \*\*理
-   WechatPay
    
    -   甜言蜜语说给左耳听
