---
project: vue-office
stars: 5077
description: 支持word(.docx)、excel(.xlsx,.xls)、pdf、pptx等各类型office文件预览的vue组件集合，提供一站式office文件预览方案，支持vue2和3，也支持React等非Vue框架。Web-based pdf, excel, word, pptx preview library
url: https://github.com/501351981/vue-office
---

vue-office
==========

支持多种文件(**docx、excel、pdf、pptx**)预览的vue组件库，支持vue2/3。也支持非Vue框架的预览。

《演示效果》

《使用非Vue框架（原生js、React等）、或者Vue里面报错，看这里》

功能特色
----

-   一站式：提供word(.docx)、pdf、excel(.xlsx, .xls)、ppt(.pptx)多种文档的在线预览方案，有它就够了
-   简单：只需提供文档的src(网络地址)即可完成文档预览
-   体验好：选择每个文档的最佳预览方案，保证用户体验和性能都达到最佳状态
-   性能好：针对数据量较大做了优化

安装
--

#docx文档预览组件
npm install @vue-office/docx vue-demi@0.14.6

#excel文档预览组件
npm install @vue-office/excel vue-demi@0.14.6

#pdf文档预览组件
npm install @vue-office/pdf vue-demi@0.14.6

#pptx文档预览组件
npm install @vue-office/pptx vue-demi@0.14.6

如果是vue2.6版本或以下还需要额外安装 @vue/composition-api

npm install @vue/composition-api

使用示例
----

文档预览场景大致可以分为三种：

-   有文档CDN地址，比如 https://\*\*\*.docx，将文档地址字符串传给组件的src属性
-   通过接口请求获取文件内容，此时可以获取文件的ArrayBuffer或Blob格式数据传给组件的src属性
-   文件上传时预览，此时可以获取文件的ArrayBuffer或Blob格式数据传给组件的src属性

docx文件预览示例 （三种使用方式均有示例）

**1\. 使用网络地址预览**

<template\>
    <vue-office-docx
        :src\="docx"
        style\="height: 100vh;"
        @rendered\="rendered"
    />
</template\>

<script\>
//引入VueOfficeDocx组件
import VueOfficeDocx from '@vue-office/docx'
//引入相关样式
import '@vue-office/docx/lib/index.css'
export default {
    components:{
        VueOfficeDocx
    },
    data(){
        return {
            docx: 'http://static.shanhuxueyuan.com/test6.docx' //设置文档网络地址，可以是相对地址
        }
    },
    methods:{
        rendered(){
            console.log("渲染完成")
        }
    }
}
</script\>

**2\. 上传文件预览**

读取文件的ArrayBuffer

<template\>
    <div\>
        <input type\="file" @change\="changeHandle"/>
        <vue-office-docx :src\="src"/>
    </div\>
</template\>

<script\>
import VueOfficeDocx from '@vue-office/docx'
import '@vue-office/docx/lib/index.css'
export default {
    components: {
        VueOfficeDocx
    },
    data(){
        return {
            src: ''
        }
    },
    methods:{
        changeHandle(event){
            let file \= event.target.files\[0\]
            let fileReader \= new FileReader()
            fileReader.readAsArrayBuffer(file)
            fileReader.onload \=  () \=> {
                this.src \= fileReader.result
            }
        }
    }
}
</script\>

**3\. 二进制文件预览**

如果后端给的不是CDN地址，而是一些POST接口，该接口返回二进制流，则可以调用接口获取文件的ArrayBuffer数据，传递给src属性。

<template\>
    <vue-office-docx
        :src\="docx"
        style\="height: 100vh;"
        @rendered\="rendered"
    />
</template\>

<script\>
//引入VueOfficeDocx组件
import VueOfficeDocx from '@vue-office/docx'
//引入相关样式
import '@vue-office/docx/lib/index.css'
export default {
    components:{
        VueOfficeDocx
    },
    data(){
        return {
            docx: ''
        }
    },
    mounted(){
        fetch('你的API文件地址', {
            method: 'post'
        }).then(res\=>{
            //读取文件的arrayBuffer
            res.arrayBuffer().then(res\=>{
                this.docx \= res
            })
        })
    },
    methods:{
        rendered(){
            console.log("渲染完成")
        }
    }
}
</script\>

excel 文件预览示例

通过网络地址预览示例如下，通过文件ArrayBuffer预览和上面docx的使用方式一致。

<template\>
    <vue-office-excel
        :src\="excel"
        style\="height: 100vh;"
        @rendered\="renderedHandler"
        @error\="errorHandler"
    />
</template\>

<script\>
//引入VueOfficeExcel组件
import VueOfficeExcel from '@vue-office/excel'
//引入相关样式
import '@vue-office/excel/lib/index.css'
export default {
    components: {
        VueOfficeExcel
    },
    data() {
        return {
            excel: 'http://static.shanhuxueyuan.com/demo/excel.xlsx'//设置文档地址
        }
    },
    methods: {
        renderedHandler() {
            console.log("渲染完成")
        },
        errorHandler() {
            console.log("渲染失败")
        }
    }
}
</script\>

pdf 文件预览示例

通过网络地址预览示例如下，通过文件ArrayBuffer预览和上面docx的使用方式一致。

<template\>
    <vue-office-pdf
        :src\="pdf"
        style\="height: 100vh"
        @rendered\="renderedHandler"
        @error\="errorHandler"
    />
</template\>

<script\>
//引入VueOfficePdf组件
import VueOfficePdf from '@vue-office/pdf'
export default {
    components: {
        VueOfficePdf
    },
    data() {
        return {
            pdf: 'http://static.shanhuxueyuan.com/test.pdf' //设置文档地址
        }
    },
    methods: {
        renderedHandler() {
            console.log("渲染完成")
        },
        errorHandler() {
            console.log("渲染失败")
        }
    }
}
</script\>

pptx 文件预览示例

通过网络地址预览示例如下，通过文件ArrayBuffer预览和上面docx的使用方式一致。

<template\>
    <vue-office-pptx
        :src\="pdf"
        style\="height: 100vh"
        @rendered\="renderedHandler"
        @error\="errorHandler"
    />
</template\>

<script\>
import VueOfficePptx from '@vue-office/pptx'
export default {
    components: {
        VueOfficePptx
    },
    data() {
        return {
            pdf: 'http://\*\*\*\*/test.pptx' //设置文档地址
        }
    },
    methods: {
        renderedHandler() {
            console.log("渲染完成")
        },
        errorHandler() {
            console.log("渲染失败")
        }
    }
}
</script\>

项目依赖的第三方库
=========

-   docx： 基于docx-preview库实现，相关issues暂不处理
-   pdf： 基于pdfjs库实现，实现了虚拟列表增加性能
-   excel: 基于exceljs 和 x-data-spreadsheet实现，全网样式支持更好
-   pptx： 基于自研库 pptx-preview 实现，源码单独付费向作者索取

我要支持作者
======

打赏加微信好友
-------

如果该项目帮到了您，节省了您宝贵的开发时间，还请您不吝给项目点个免费的赞。

当然了，如果您能请作者喝杯咖啡，哪怕喝瓶娃娃哈矿泉水，也是对作者最真诚的鼓励，打赏用户欢迎添加微信，后续交流前端相关问题。

如果您有问题要咨询或者解决，可打赏咨询作者，自2024年12月起，可能不会及时处理issues内容，作者也要吃饭，也面临大龄程序员困境。

掘金小册
----

凝聚作者近10年工作经验的掘金小册《如何写出高质量的前端代码》 已经上线啦，欢迎前端同学关注，希望能够提升大家的前端编码水平。

小册已售 1200+份，收到前端同学的高度评价，对提升日常开发效率和质量，有非常大的帮助。
