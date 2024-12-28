---
project: f-render
stars: 1588
description: f-render | 基于 ElementUI 的表单设计器
url: https://github.com/dream2023/f-render
---

f-render | 基于 ElementUI 的表单设计器
==============================

-   交流群
-   介绍
-   注意
-   特性
-   Demo
-   教程
-   1 分钟快速接入
    -   第 1 步：安装
    -   第 2 步：注册
    -   第 3 步：使用
-   用户模式
    -   基于 f-render 的配置
    -   基于 vue-ele-form 的配置
-   定制化
    -   新增官方扩展组件（以富文本扩展为例）
        -   安装组件
        -   注册组件
        -   配置属性
    -   新增自定义组件
        -   创建组件并全局注册
        -   书写配置
        -   合并配置并传入
    -   定制化原组件配置 & 表单配置
    -   定制化右侧 Tabs
    -   样式定制化
-   二次开发
-   f-render 问答集锦
-   Props 说明
-   插槽
-   生态
-   特别感谢赞助者
-   Contributors ✨

介绍
--

f-render 是基于 vue-ele-form 开发的可视化表单设计工具, 适用于 各种流程引擎和动态表单项目，大大节省你的开发时间；

注意
--

注意，此设计器不是独立存在的，是依托于 vue-ele-form，在使用前请务必阅读 vue-ele-form 的文档。

特性
--

-   组件方式：以组件方式接入，1 分钟轻松接入；
-   体积小：Gzip 压缩后 `100k` 左右；
-   易扩展：可以在`不更改源码`的情况下增删改属性、组件；

Demo
----

https://dream2023.gitee.io/f-render/

教程
--

虽然 f-render 可以做到在不更改源码的情况下实现大量的定制化，但是依然有不少人希望能够根据公司的需求进行二次开发。

所以我推出了一个从 0 实现整个项目的 教程，如果感兴趣 f-render 的实现过程和思考，可以点击 从 0 实现可视化表单组件 进行学习。

1 分钟快速接入
--------

#### 第 1 步：安装

yarn add element-ui  # npm install element-ui -S
yarn add vue-ele-form # npm install vue-ele-form -S
yarn add f-render # npm install f-render -S

#### 第 2 步：注册

// vue-ele-form 的注册可参考：https://www.yuque.com/chaojie-vjiel/vbwzgu/xl46cd
import EleForm from "vue-ele-form";
import FRender from "f-render";
import ElementUI from "element-ui";
import "element-ui/lib/theme-chalk/index.css";

Vue.use(ElementUI);
Vue.use(EleForm);
Vue.component("f-render", FRender);

#### 第 3 步：使用

<template\>
  <f-render
    @save\="handleSave"
    :loading\="loading"
    height\="calc(100vh - 60px)"
    :config\="formConfig"
  />
</template\>

<script\>
  export default {
    data() {
      return {
        loading: false,
        formConfig: {}
      };
    },
    methods: {
      handleSave(res) {
        // 这里是保存到 localStorage，你可以保存到服务器
        localStorage.setItem("form-config", res);
        this.$message.success("保存成功啦~");
      }
    },
    mounted() {
      // 模拟异步加载
      this.loading \= true;
      setTimeout(() \=> {
        this.loading \= false;
        this.formConfig \= localStorage.getItem("form-config") || "";
      }, 1000);
    }
  };
</script\>

用户模式
----

我们把动态表单分为两个阶段：

-   首先是设计阶段：通过拖拽设计表单；
-   然后是用户阶段：将设计好的表单以纯表单的形式让用户填写。

我们别分称这两个阶段的表单为设计模式和用户模式。设计模式的表单配置我们已经讲了，下面看用户模式下的表单配置：

#### 基于 f-render 的配置

通过属性 `pure`, 可以直接做为表单使用，其数据提交方式同 `vue-ele-form` 一样，具体可查看文档。

<template\>
  <f-render
    v-model\="formData"
    :request-fn\="handleSubmit"
    @request-success\="handleSuccess"
    :config\="formConfig"
    pure
  />
</template\>

<script\>
  export default {
    data() {
      return {
        formData: {},
        formConfig: ""
      };
    },
    methods: {
      handleSubmit(data) {
        // eslint-disable-next-line no-console
        console.log(data);
        return Promise.resolve();
      },
      handleSuccess() {
        this.$message.success("创建成功");
      }
    },
    mounted() {
      // 模拟异步加载
      this.loading \= true;
      setTimeout(() \=> {
        this.loading \= false;
        this.formConfig \= localStorage.getItem("form-config") || "";
      }, 1000);
    }
  };
</script\>

#### 基于 vue-ele-form 的配置

如果你的可视化设计和表单使用，不再一个系统，可以直接使用 `vue-ele-form`，不必安装 `f-render`，具体如下：

<template\>
  <ele-form
    v-model\="formData"
    :request-fn\="handleSubmit"
    @request-success\="handleSuccess"
    v-if\="formConfig"
    v-bind\="formConfig"
  />
</template\>

<script\>
  export default {
    data() {
      return {
        formData: {},
        formConfig: null
      };
    },
    methods: {
      handleSubmit(data) {
        // eslint-disable-next-line no-console
        console.log(data);
        return Promise.resolve();
      },
      handleSuccess() {
        this.$message.success("创建成功");
      }
    },
    mounted() {
      // 模拟异步加载
      setTimeout(() \=> {
        try {
          // 这里必须对字符串进行反序列化
          this.formConfig \= eval(\`(${localStorage.getItem("form-config")})\`);
        } catch {
          this.$message.error("数据解析失败");
        }
      }, 1000);
    }
  };
</script\>

定制化
---

### 新增官方扩展组件（以富文本扩展为例）

#### 安装组件

yarn add vue-ele-form-quill-editor

#### 注册组件

Vue.component("quill-editor", EleFormQuillEditor);

#### 配置属性

<template\>
  <!-- 省略其它属性 -->
  <f-render :comps\="comps" />
</template\>

<script\>
  // 默认配置
  import comps from "f-render/src/fixtures/comps";
  // 富文本配置
  import quillEditor from "f-render/src/fixtures/extends/quill-editor";
  // 可以更改显示组件位置，默认为 10
  // 这里更改为 2，显示更靠前
  quillEditor.sort \= 2;

  export default {
    data() {
      return {
        // 拼接上即可
        comps: comps.concat(quillEditor)
      };
    }
  };
</script\>

### 新增自定义组件

#### 创建组件并全局注册

需要根据 vue-ele-form 文档创建自定义组件，并注册。

#### 书写配置

你可以参考源码中的配置，一下是范例和属性说明：

// custom-url.js
export default {
  // 假如这个组件叫 url（必填）
  type: "custom-url",
  // 默认标签名（必填）
  label: "URL",
  // 用于排序，值越小，越靠前
  sort: 1,
  // 属性配置
  config: {
    // 属性配置说明地址（可省略）
    url: "https://www.xxx.com",
    // 组件属性配置（不知道啥是组件属性，可以看一下界面右侧）
    attrs: {
      // config 配置 参考 FormDesc:
      // https://www.yuque.com/chaojie-vjiel/vbwzgu/iw5dzf#KOPkD
      config: {
        // max 为属性名
        max: {
          type: "number",
          label: "最大输入长度"
        },
        name: {
          type: "input",
          label: "原生 name",
          // 必填
          required: true
        }
        // ....
      },
      // 默认值，如果在配置文件里设置了，则每个组件都会携带
      data: {
        name: "url"
      }
    },
    // 表单项配置，是 FormDesc 中非 attrs 的其它配置，
    // 具体可看：https://www.yuque.com/chaojie-vjiel/vbwzgu/iw5dzf#hl4pm
    common: {
      config: {
        // 默认值
        default: {
          type: "input",
          label: "默认值"
        }
      },
      data: {}
    }
  }
};

#### 合并配置并传入

<template\>
  <!-- 省略其它属性 -->
  <f-render :comps\="comps" />
</template\>

<script\>
  import comps from "f-render/src/fixtures/comps";
  import customUrl from "some/path/custom-url";
  export default {
    data() {
      return {
        comps: comps.concat(customUrl)
      };
    }
  };
</script\>

### 定制化原组件配置 & 表单配置

-   组件配置目录：`f-render/src/fixtures/comps.js`
-   表单配置目录：`f-render/src/fixtures/form-props.js`
-   表单项通用属性配置：`f-render/src/fixtures/form-item-common.js`
-   扩展组件目录：`f-render/src/fixtures/extends/[扩展组件名].js`

如果你想修改组件属性或者表单的属性，减少或者增加组件，可以将上述文件`拷贝到自己的项目`目录，参考上述配置说明，进行更改，并传入即可：

<!-- formProps 是表单属性 -->
<!-- comps 是组件列表和属性 -->
<!-- formItemCommon 是表单项通用属性配置 -->
<f-render
  :form-props\="formProps"
  :comps\="comps"
  :form-item-common\="formItemCommon"
/>

具体而言，如果想让每个 `input` 组件都携带 `clearable: true` 的属性，我们可以这样操作：

<template\>
  <!-- 其它属性省略 -->
  <!-- 将更改后的 comps 传递过去即可 -->
  <f-render :comps\="comps" />
</template\>

<script\>
  import comps from "f-render/src/fixtures/comps";
  // 查找 input 组件，当然你也可以看源码，直接查看索引
  const inputIndex \= comps.findIndex(item \=> item.type \=== "input");
  // 更改 config.attrs.data 值即可
  comps\[inputIndex\].config.attrs.data \= { clearable: true };

  export default {
    data() {
      return {
        comps
      };
    }
  };
</script\>

### 定制化右侧 Tabs

我们可以通过 `isShowRight` 属性来控制右侧面板是否显示，通过 `rightTabs` 来定制具体显示的面板名称，具体如下：

<template\>
  <!-- 定制化右侧 tabs -->
  <f-render :right-tabs\="tabs" />
</template\>

<script\>
  export default {
    data() {
      return {
        tabs: \[
          { label: "表单项属性配置", name: "form-item-common" },
          { label: "组件属性配置", name: "form-item-attrs" }
          // 注释下面的内容，就可以不显示
          // { label: "表单配置", name: "form-props" }
        \]
      };
    }
  };
</script\>

### 样式定制化

直接进行样式覆盖即可，注意不要加 `scoped`，否则覆盖不成功

二次开发
----

如果仅通过`属性`和`样式`定制化已无法满足的你和你产品经理的要求，那就需要进行定制化开发，我个人觉得代码整体还是非常简单的，你可以 `clone` 代码或者下载后（建议用gitee），进行相应的更改，更改后有两种处理方式:

-   直接放到项目目录里，并将安装 `dependencies` 的依赖复制到项目，进行开发即可；
-   直接开发，然后发布到公司私服，如果是开源，则可以发到 GitHub 或者 gitee，然后安装自己的即可

具体的细节，开头提的教程里会有详细的过程，希望大家可以支持一下。

f-render 问答集锦
-------------

-   1、f-render 不能做什么？
-   2、怎么实现 options URL 配置？

Props 说明
--------

props: {
  // 表单内容
  config: {
    type: \[Object, String\],
    required: true
  },
  // 设计器整体高度
  height: {
    type: \[String, Number\],
    default: "400px"
  },
  // 保存格式
  saveFormat: {
    type: String,
    default: "string",
    validator(val) {
      return \["object", "string"\].includes(val);
    }
  },
  // 是否纯净（用于显示表单）
  pure: Boolean,
  // 表单配置
  formProps: {
    type: Object,
    default: () \=> formProps
  },
  // 表单项配置
  formItemCommon: {
    type: Object,
    default: () \=> formItemCommonDefault
  },
  // 组件列表
  comps: {
    type: Array,
    default: () \=> comps
  },
  // 操作配置
  operations: {
    type: Array,
    default: () \=> \["preview", "data", "code", "batch", "clear", "save"\]
  },
  // 是否显示右侧
  isShowRight: {
    type: Boolean,
    default: true
  },
  // 右侧属性面板 Tabs
  rightTabs: {
    type: Array,
    default: () \=> \[
      { label: "表单项属性配置", name: "form-item-common" },
      { label: "组件属性配置", name: "form-item-attrs" },
      { label: "表单配置", name: "form-props" }
    \]
  },
  // 是否在加载
  loading: Boolean,

  // 表单相关（pure 为 true 时）, 同 vue-ele-form
  // https://www.yuque.com/chaojie-vjiel/vbwzgu/dyw8a7
  requestFn: Function,
  isLoading: Boolean,
  formError: Object,
  // ....
},

插槽
--

-   left：左侧组件列表
-   main: 中间区域
-   main-header: 头部操作区
-   main-content: 表单设计区
-   right: 右侧属性配置区

举例：

<template\>
  <f-render\>
    <!-- 左侧插槽 -->
    <template v-slot:left\="{frender}"\>
      <div\>
        <div\>left</div\>
        <div\>{{frender.comps}}</div\>
      </div\>
    </template\>
  </f-render\>
  <template\></template
\></template\>

其中 `frender` 数据是 `f-render` 组件数据的集合，具体都有哪些数据，可以参考源码，其它插槽均有此参数。

生态
--

Project

Status

Description

vue-ele-form

接基于 ElementUI 的数据驱动表单

f-render

专为 vue-ele-form 开发的可视化表单设计工具

vue-ele-form-json-editor

JSON 编辑器(vue-ele-form 扩展)

vue-ele-form-upload-file

upload 文件上传组件(vue-ele-form 扩展)

vue-ele-form-image-uploader

上传图片增强组件(vue-ele-form 扩展)

vue-ele-form-tree-select

树形选择框组件(vue-ele-form 扩展)

vue-ele-form-table-editor

表格编辑器(vue-ele-form 扩展)

vue-ele-form-dynamic

动态表单(vue-ele-form 扩展)

vue-ele-form-video-uploader

上传视频增强组件(vue-ele-form 扩展)

vue-ele-form-quill-editor

富文本编辑器(vue-ele-form 扩展)

vue-ele-form-markdown-editor

markdown 编辑器(vue-ele-form 扩展)

vue-ele-form-bmap

百度地图组件(vue-ele-form 扩展)

vue-ele-form-codemirror

代码编辑器(vue-ele-form-gallery 扩展)

vue-ele-form-gallery

图片/视频展示组件(vue-ele-form 扩展)

vue-ele-form-data-editor

轻量级数据编辑器(vue-ele-form 扩展)

特别感谢赞助者
-------

优客服

圣捷远创

damonnie

xzusoft

seeenter

高亢

> 如果您觉得对您有所帮助, 可以请作者喝一杯咖啡, 让开源走的更远, 点击进入码云赞赏一下, 并加入下面交流群, 将链接发送给我

Contributors ✨
--------------

Thanks goes to these wonderful people (emoji key):

  
**张超杰**  
📖 💻 🤔

  
**Wisen**  
💻

  
**IWANABETHATGUY**  
💻

This project follows the all-contributors specification. Contributions of any kind welcome!
