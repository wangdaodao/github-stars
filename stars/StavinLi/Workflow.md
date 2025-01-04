---
project: Workflow
stars: 1536
description: 仿钉钉审批流程设置
url: https://github.com/StavinLi/Workflow
---

### workflow钉钉审批流程设置

workflow钉钉审批流程设置，基于vue开发。 QQ交流群①:639251756 QQ交流群②:790780565

-   开源地址vue2版本 https://github.com/StavinLi/Workflow github点个星吧！
-   开源地址vue3版本 https://github.com/StavinLi/Workflow-Vue3 github点个星吧！
-   开源地址react版本 https://github.com/StavinLi/Workflow-React github点个星吧！
-   预览地址 https://stavinli.github.io/Workflow/dist/index.html#/

* * *

#### 项目介绍

-   UI钉钉风格
-   技术点

1.  组件自调用+递归处理，按树状结局处理审批流程问题

-   主要功能点

1.  界面缩放

<div class\="zoom"\>
	<div :class\="'zoom-out'+ (nowVal==50?' disabled':'')" @click\="zoomSize(1)"\></div\>
    <span\>{{nowVal}}%</span\>
    <div :class\="'zoom-in'+ (nowVal==300?' disabled':'')" @click\="zoomSize(2)"\></div\>
</div\>

1.  节点设置（包括审批人、发起人、抄送人、条件设置）

<el-drawer title\="审批人设置" :visible.sync\="approverDrawer" direction\="rtl" class\="set\_promoter" size\="550px" :before-close\="saveApprover"\> 
    <div class\="demo-drawer\_\_content"\>
        <div class\="drawer\_content"\>
            <div class\="approver\_content"\>
                <el-radio-group v-model\="approverConfig.settype" class\="clear" @change\="changeType"\>
                    <el-radio :label\="1"\>指定成员</el-radio\>
                    <el-radio :label\="2"\>主管</el-radio\>
                    <el-radio :label\="4"\>发起人自选</el-radio\>
                    <el-radio :label\="5"\>发起人自己</el-radio\>
                    <el-radio :label\="7"\>连续多级主管</el-radio\>
                </el-radio-group\>
                ...

1.  节点新增

<div class\="add-node-btn"\>
    <el-popover placement\="right-start" v-model\="visible"\>
          <div class\="add-node-popover-body"\>
              <a class\="add-node-popover-item approver" @click\="addType(1)"\>
                  <div class\="item-wrapper"\>
                      <span class\="iconfont"\></span\>
                  </div\>
                  <p\>审批人</p\>
              </a\>
              <a class\="add-node-popover-item notifier" @click\="addType(2)"\>
                  <div class\="item-wrapper"\>
                      <span class\="iconfont"\></span\>
                  </div\>
                  <p\>抄送人</p\>
              </a\>
              <a class\="add-node-popover-item condition" @click\="addType(4)"\>
                  <div class\="item-wrapper"\>
                      <span class\="iconfont"\></span\>
                  </div\>
                  <p\>条件分支</p\>
              </a\>
          </div\>
          ...

5.错误校验

let {type,error,nodeName,conditionNodes} \= childNode
if (type \== 1 || type \== 2) {
    if (error) {
        this.tipList.push({ name: nodeName, type: \["","审核人","抄送人"\]\[type\] })
    }
    this.reErr(childNode)
} else if (type \== 3) {
    this.reErr(childNode)
} else if (type \== 4) {
    this.reErr(childNode)
    for (var i \= 0; i < conditionNodes.length; i++) {
        if (conditionNodes\[i\].error) {
            this.tipList.push({ name: conditionNodes\[i\].nodeName, type: "条件" })
        }
        this.reErr(conditionNodes\[i\])
    }
}

6.模糊搜索匹配人员、职位、角色

<input type\="text" placeholder\="搜索成员" v-model\="searchVal" @input\="getDebounceData($event,activeName)"\>
<input type\="text" placeholder\="搜索角色" v-model\="searchVal" @input\="getDebounceData($event,2)"\>
<input type\="text" placeholder\="请选择具体人员/角色/部门" v-if\="conditionConfig.nodeUserList.length == 0" @click\="addConditionRole"\>

#### 项目安装

> git clone https://github.com/StavinLi/Workflow.git 点个赞吧！

#### 项目运行 **node14**

> 1.环境依赖 `npm i`

> 2.本地运行 `npm run serve`

> 3.打包运行 `npm run build`
