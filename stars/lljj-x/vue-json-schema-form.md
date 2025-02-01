---
project: vue-json-schema-form
stars: 2114
description: 基于Vue/Vue3，Json Schema 和 ElementUi/antd/iview3/naiveUi 等生成 HTML Form 表单，用于活动编辑器、h5编辑器、cms等数据配置；支持可视化生成表单Schema 。 Generate a form using Vue/Vue3, Json Schema and ElementUi/antdv/iview3/naiveUi
url: https://github.com/lljj-x/vue-json-schema-form
---

vue-json-schema-form
--------------------

基于 Vue2 / Vue3、 JSON Schema 生成带完整校验的Form表单，你的 🌟 🌟 🌟 就是最大的支持

查看文档 - Playground - 可视化表单Schema生成器

ui框架支持
------

-   vue2 ElementUi
-   vue2 Iview3
-   vue3 Element Plus
-   vue3 Antdv
-   vue3 NaiveUi

交流群
---

QQ群：`146845780`，_反应不及时🙄_

**使用问题请优先通过 Github issue 提交**

如何启动相关编辑器页面
-----------

-   **_活动编辑器项目已经独立了新的仓库，请直接使用 https://github.com/lljj-x/vjsf-demo-editor_**
-   **_活动编辑器项目已经独立了新的仓库，请直接使用 https://github.com/lljj-x/vjsf-demo-editor_**

1、 安装依赖

```
yarn install
```

2、 同时运行 `Playground/表单Schema生成器/活动编辑器`

```
# Playground http://127.0.0.1:8800/
# 可视化表单Schema编辑器 http://127.0.0.1:8800/schema-generator.html
# （H5）活动编辑器 http://127.0.0.1:8800/vue-editor.html

yarn run demo:dev
```

3、 单个运行（指定entry编译更快）

```
# 只运行 Playground
yarn run demo:dev --dir=index

# 只运行 表单Schema生成器
yarn run demo:dev --dir=schema-generator

# 只运行（H5）活动编辑器
yarn run demo:dev --dir=vue-editor
```

### 说明

-   遵循 `JSON Schema` 规范，只需要给定 `JSON Schema`，即可生成对应的form表单
-   快速配置个性化ui视图和校验错误信息，可适配常用的ui库
-   表单schema校验使用 ajv
-   设计思想和对schema解析索引参考 react-jsonschema-form

相关资料
----

JSON Schema | Vue

### 为何开发

在做前端可视化编辑时，为了解决数据配置表单的通用性，所以使用 `JSON Schema` 描述数据结构，动态生成表单。

这样做的好处除了解决在每个配置表单的重复工作，服务端也可以基于同一份schema保持和前端一致的校验规则，不过对于使用 vue elementUi并未找到合适库可以直接使用，所以在后面一段时间决定自己实现一个 。

问题或建议
-----

-   标准 JSON Schema 不支持部分和更新计划

有任何使用问题或者建议都可以通过 Github issue 提交给我

License
-------

Apache-2.0
