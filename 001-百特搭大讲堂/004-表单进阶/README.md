---
title: "表单进阶"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/ldtgixglz52risvg"
visible: true
slug: "ldtgixglz52risvg"
doc_id: 189591467
updated_at: "2026-03-25T09:10:21.000Z"
breadcrumb:
  - "百特搭大讲堂"
  - "表单进阶"
---
<a id="P9gtv"></a>


## 表单生命周期

<a id="JmWpL"></a>


### 加载


![加载页面​加载页面定义初始化页面引擎​开启异步加载明细表是​结束engine-initialized页面加载前加载主表数据engine-mounted页面加载时渲染组件同步加载子表数据否页面控件赋值异步加载子表数据并行处理页面控件赋值渲染异步结束异步结束控件事件但不触发事件：change、list-change​](../../_assets/ldtgixglz52risvg/diagram-afa2942629.jpeg)

<a id="kgcta"></a>


#### 前端：engine-initialized 页面加载前事件


[DataView 表单页](../../006-前端开发/002-前端组件属性及事件/005-DataView 表单页/README.md#ncTmV)

<a id="VaoM0"></a>


#### 前端：engine-mounted 页面加载时事件


[DataView 表单页](../../006-前端开发/002-前端组件属性及事件/005-DataView 表单页/README.md#miTjE)

<a id="QRyb7"></a>


### 提交


![点击保存按钮​表单控件校验​数据发送结束​engine-submit表单提交前engine-submit-params表单提交时engine-submitted表单提交后点击流程审批按钮approval:onBeforeBtnClick表单控件校验数据发送保存数据操作项执行前操作项执行后保存数据驱动流程结束流程图节点事件](../../_assets/ldtgixglz52risvg/diagram-79cde424ee.jpeg)

<a id="nLaAL"></a>


#### 前端：approval:onBeforeBtnClick


[DataView 表单页](../../006-前端开发/002-前端组件属性及事件/005-DataView 表单页/README.md#EDfFY)

<a id="YZhb4"></a>


#### 前端：engine-submit 表单提交前


[DataView 表单页](../../006-前端开发/002-前端组件属性及事件/005-DataView 表单页/README.md#EmblV)

<a id="KIhJG"></a>


#### 前端：engine-submit-params 表单提交时


[DataView 表单页](../../006-前端开发/002-前端组件属性及事件/005-DataView 表单页/README.md#oSPnB)

<a id="h5wPY"></a>


#### 前端：engine-submitted 表单提交后


[DataView 表单页](../../006-前端开发/002-前端组件属性及事件/005-DataView 表单页/README.md#NzTDv)

<a id="zIgoi"></a>


#### 后端：操作项执行前

<a id="gaO5h"></a>


#### 后端：操作项执行后

<a id="ey7fm"></a>


#### 后端：流程图节点事件

## 下级条目

- [表单上引入第三方组件](001-表单上引入第三方组件.md)
- [JS 取值、赋值操作](002-JS 取值、赋值操作/README.md)
- [如何从表单上打开其他表单](003-如何从表单上打开其他表单.md)
- [如何调用接口](004-如何调用接口/README.md)
- [使用Vue容器](005-使用Vue容器/README.md)
- [替换下拉框的默认查询](006-替换下拉框的默认查询.md)
- [表单有效性校验](007-表单有效性校验/README.md)
- [表单保存后处理](008-表单保存后处理.md)
- [自定义打印](009-自定义打印.md)
- [自定义组件开发](010-自定义组件开发/README.md)
- [表单设置默认值](011-表单设置默认值.md)
