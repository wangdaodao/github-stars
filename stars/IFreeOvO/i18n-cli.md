---
project: i18n-cli
stars: 166
description: 支持将vue、react项目里的中文替换成 i18n 国际化标记，并支持自动翻译的命令行工具
url: https://github.com/IFreeOvO/i18n-cli
---

介绍
==

该项目是一个支持将中文替换成 i18n 国际化标记，并支持自动翻译的命令行工具

流程设计
----

见掘金文章

功能
--

-   支持.mjs.cjs.js.ts.jsx.tsx.vue 后缀文件提取中文
-   支持 vue2.0，vue3.0，react 提取中文
-   支持通过/\*i18n-ignore\*/注释，忽略中文提取
-   支持将提取的中文以 key-value 形式存入\*.json 语言包里
-   支持 prettier 格式化代码
-   支持将中文语言包自动翻译成其他语言
-   支持将翻译结果导出成 excel
-   支持读取 excel 文件并转换成语言包
-   自定义语言包 key 的层级嵌套
-   自定义语言包的 key
-   自定义 i18n 工具的调用对象
-   自定义 i18n 工具的方法名
-   自定义 i18n 第三方包的导入
-   自定义忽略提取的方法

安装
--

```
npm i @ifreeovo/i18n-extract-cli -g
```

使用文档
----

点击这里

转换效果示例
------

#### react 转换示例

转换前

import { useState } from 'react'

/\*i18n-ignore\*/
const b \= '被忽略提取的文案'

function Example() {
  const \[msg, setMsg\] \= useState('你好')

  return (
    <div\>
      <p title\="标题"\>{msg + '呵呵'}</p\>
      <button onClick\={() \=> setMsg(msg + '啊')}\>点击</button\>
    </div\>
  )
}

export default Example

转换后

import { t } from 'i18n'
import { useState } from 'react'

/\*i18n-ignore\*/
const b \= '被忽略提取的文案'

function Example() {
  const \[msg, setMsg\] \= useState(t('你好'))
  return (
    <div\>
      <p title\={t('标题')}\>{msg + t('呵呵')}</p\>
      <button onClick\={() \=> setMsg(msg + t('啊'))}\>{t('点击')}</button\>
    </div\>
  )
}
export default Example

#### vue 转换示例

转换前

<template\>
  <div :label\="'标签'" :title\="1 + '标题'"\>
    <p title\="测试注释"\>内容</p\>
    <button @click\="handleClick('信息')"\>点击</button\>
  </div\>
</template\>

<script\>
export default {
  methods: {
    handleClick() {
      console.log('点了')
    },
  },
}
</script\>

转换后

<template\>
  <div :label\="$t('标签')" :title\="1 + $t('标题')"\>
    <p :title\="$t('测试注释')"\>{{ $t('内容') }}</p\>
    <button @click\="handleClick($t('信息'))"\>{{ $t('点击') }}</button\>
  </div\>
</template\>
<script\>
export default {
  methods: {
    handleClick() {
      console.log(this.$t('点了'))
    },
  },
}
</script\>

开源许可证
-----

MIT
