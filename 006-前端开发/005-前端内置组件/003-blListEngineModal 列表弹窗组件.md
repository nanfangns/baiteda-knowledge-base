---
title: "blListEngineModal 列表弹窗组件"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/en5pbeb4pm411fa0"
visible: true
slug: "en5pbeb4pm411fa0"
doc_id: 187622054
updated_at: "2024-10-11T06:56:27.000Z"
breadcrumb:
  - "前端开发"
  - "前端内置组件"
  - "blListEngineModal 列表弹窗组件"
---
<a id="DKQU3"></a>


# 1.属性

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| 属性 | 说明 | 类型 | 必填 | 默认值 | version |
| visible(v-model) | 弹窗是否可见 | boolean |  | false | ​ |
| formKey | 列表的formKey | string | 是 |  |  |
| appId | 应用的appId | string | 是 |  |  |
| title | 弹窗的标题 | string |  |  |  |
| rowIndex | 弹窗在明细表内的下标 | number | 在明细表内必填 |  |  |
| selection | 是否可选择 | boolean |  | false | ​ |
| [onEngineBeforeInit](../002-前端组件属性及事件/006-ListView 列表页/README.md#A9qX5) | 表单加载前的回调函数 | (innerCtx: Engine,payload:EventPayload) => void | 否 | ​ | 5.2.0+ |
| onEngineInit | 表单初始化的回调方法，在里边可以修改一些显示隐藏或默认的数据过滤等等 | (innerCtx: Engine) => void |  |  |  |
| onOk | 点击确定方法， selection参数为true的时候，回调可以接收到当前选中的数据，false时，拿不到任何数据 | (selectState?: SelectStateType | undefined) => void |  |  |  |
| 以下参数都是在开启selection的情况下才会生效 |  |  |  |  |  |
| value | 需要回显的选中值选中的值，单选是string，多选是string[] | string | string[] |  |  |  |
| multiple | 多选 | boolean |  | false | ​ |
| valueKey | 目标存储值在模型中的key | string |  | 不传则根据列表所对应的模型主键 | ​ |

<a id="sUGLJ"></a>


# 2.示例代码


```html
<bl-list-engine-modal
	v-model:visible="visible"
	:value="value"
	:title="instance.props.content"
	selection
	:multiple="instance.props.fillBack.multiple"
	:app-id="instance.props.listPageBind.appId"
	:form-key="instance.props.listPageBind.formKey"
	:row-index="rowIndex"
	:on-ok="handlerClickOk"
	:on-engine-init="onEngineInit"
  :onEngineBeforeInit="onEngineBeforeInit"
></bl-list-engine-modal>
```
