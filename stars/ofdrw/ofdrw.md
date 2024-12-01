---
project: ofdrw
stars: 1397
description: OFD Reader & Writer 开源的OFD处理库，支持文档生成、数字签名、文档保护、文档合并、转换、导出等功能，文档格式遵循《GB/T 33190-2016 电子文件存储与交换格式版式文档》。
url: https://github.com/ofdrw/ofdrw
---

OFD Reader & Writer
===================

在使用OFDRW前，请务必悉知 _**《OFD Reader & Writer免责声明》**_！

> 若clone和文档预览存在困难，请移步 https://gitee.com/ofdrw/ofdrw

**Talk is cheap,Show me the code. ——Linus Torvalds**

OFD Reader & Writer 开源的OFD处理库，支持文档生成、数字签名、文档保护、文档合并、转换、导出等功能。

本项目采用Apache 2.0许可，请尊重开源项目作者，在软件中附带OFDRW开源软件许可，**在遵守开源协议前提下可免费商业化使用**。

根据《GB/T 33190-2016 电子文件存储与交换格式版式文档》标准实现版式文档OFD库（含有书签）。

项目采用Maven模块管理，各模块如下：

-   **ofdrw-core** OFD核心API，参考《GB/T 33190-2016 电子文件存储与交换格式版式文档》实现的基础数据结构。
-   **ofdrw-font** 生成OFD字体相关。
-   **ofdrw-layout** OFD布局引擎库，用于文档构建和渲染。
-   **ofdrw-pkg** OFD文件的容器，用于文档的打包。
-   **ofdrw-reader** OFD文档解析器，用于OFD的反序列化以及签名签章。
-   **ofdrw-sign** OFD文档数字签章。
-   **ofdrw-gm** 用于支持签章模块需要的国密电子签章数据结构。
-   **ofrw-crypto** 用于实现《GM/T 0099-2020 开放版式文档密码应用技术规范》对OFD的密码相关功能。
-   **ofdrw-gv** OFDRW 所有模块所共用的全局变量。
-   **ofdrw-converter** OFD文档转换。
-   **ofdrw-tool** OFD文档工具，文档合并、裁剪、重组、混合。_**New**_
-   **ofdrw-graphics2d** 实现了AWT Graphics2D接口，生成OFD文档内容。
-   **ofdrw-full** 上述所有模块整合包，用于简化依赖引入。

注：

-   您可以根据需求裁剪模块优化程序体积。
-   您可以仅引用`ofdrw-core`中定义的数据结来构建属于您自己的OFD库，就像ofdrw-graphics2d那样。

QuickStart
----------

Maven项目引入依赖

<dependency\>
  <groupId\>org.ofdrw</groupId\>
  <artifactId\>ofdrw-full</artifactId\>
  <version\>2.3.4</version\>
</dependency\>

**OFDRW 将持续保证API的向下兼容，您可以放心的升级OFDRW库至最新版本。**

> -   若您没有采用Maven管理项目，请参阅项目中`pom.xml`文件中的依赖，手动解决三方依赖包问题。
> -   若出现NoClassFound等错误，请检查相关包是否存在冲突。

如何生成一份OFD文档，如何把大象放入冰箱？

public class HelloWorld {
    public static void main(String\[\] args) throws IOException {
        Path path = Paths.get("HelloWorld.ofd");
        try (OFDDoc ofdDoc = new OFDDoc(path)) {
            Paragraph p = new Paragraph("你好呀，OFD Reader&Writer！");
            ofdDoc.add(p);
        }
        System.out.println("生成文档位置: " + path.toAbsolutePath());
    }
}

效果如下：

-   文档生成API示例
-   文档布局示例
-   Canvas示例
-   文字抽取示例
-   段落布局示例
-   文档编辑示例
-   数字签名清理示例

相关文档目录：

-   OFD R&W 布局设计
-   OFD R&W 扩展 自定义元素
-   OFD R&W 基于Canvas文档内容生成
-   OFD R&W 签名签章快速入门
-   OFD R&W 加密 完整性保护协议
-   OFD R&W 转换OFD/OFD导出
-   OFD R&W 字形数据解析
-   OFD R&W 文档合并
-   OFD R&W 区域占位区块（类表单效果）
-   OFD R&W 单元格元素 使用指南
-   OFD R&W 内容生成 事件处理
-   OFD R&W 附件操作
-   OFD R&W 添加水印

### 相关解决方案

#### HTML5

HTML5前端预览解决方案：

-   DLTech21/ofd.js . https://github.com/DLTech21/ofd.js
-   xxss0903/LiteOfd . https://github.com/xxss0903/liteofd

#### 开源阅读器

**XilouReader**：chingliu/XilouReader . https://gitee.com/chingliu/XilouReader

-   基于pdfium的ofd/pdf双引擎版式阅读器。

**OfdiumEx**：roy19831015/OfdiumEx . https://github.com/roy19831015/OfdiumEx

-   基于cairo库渲染OFD。
-   Windows客户端阅读器

#### 图片转换

> 目前已经被合并到`ofdrw-converter` 模块

推荐开源OFD图片转换解决方案： QAQtutu/ofdbox . https://github.com/QAQtutu/ofdbox

-   支持OFD解析。
-   基于java.awt解析OFD实现图片绘制。

#### 阅读器

阅读器方面，您也可以尝试：

-   数科网维公司 . 数科OFD阅读器 . www.ofd.cn
-   Foxit . 福昕OFD . www.foxitsoftware.cn/ofd/

源码安装
----

> 支持 _**JDK 1.8**_ 及以上版本构建。

在项目根目录下运行：

mvn install

就可以完成项目的构建打包，安装到本地Maven仓库中。

社区交流
----

_**Share and Communicate**_

为方便社区建设与交流，提供社区QQ群：

-   05群号： **762837395**
-   04群号： **690642037**（满）
-   03群号： **717320255**（满）
-   02群号： **745517934**（满）
-   01群号： **577682453**（满）

> -   若您遇到与OFD相关的技术问题，欢迎进群交流!
> -   若您对项目有建设性意见或方案欢迎提交**Issue**与**Pull Request**。

参与贡献
----

参与贡献代码尽量遵守下面代码规约：

1.  **原则上禁止`public`方法、类、接口进行删除**：为了保留向下兼容性，如果是更新升级请标注过去已经暴露方法、接口、类为过时标记`@Deprecated`，并注释置新的实现位置`@deprecated {@link SomethingNew}`。
2.  **请为每个`public`方法、类、接口添加注释**：为了保留开发者的便利性，注释一般为多行注释，注释内容需要包含参数以及方法或类的作用、参数意义、返还值以及意义、异常抛出、以及参数意义。

\>> GitHub 第一次参与开源(多语言)

> -   贡献指南。

项目情况
----

### 进展

\>> 项目进展

> 在OFDRW 2.0.0之后，项目进展以发布说明的方式在项目托管仓库中描述。

### 项目关注度

> 项目获得 Star曲线