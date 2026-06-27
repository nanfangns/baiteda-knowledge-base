---
title: "ListPageBtnCreateForm 创建按钮"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/hqog4fo1rmkm6h23"
visible: true
slug: "hqog4fo1rmkm6h23"
doc_id: 187622047
updated_at: "2024-10-10T01:39:04.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "ListView 列表页"
  - "ListPageBtnCreateForm 创建按钮"
---
<a id="bMYN2"></a>


## 属性

<a id="oqWV1"></a>


## 事件

<a id="kc5Bk"></a>


### click 点击时

<a id="DenjG"></a>


#### 函数返回值

- return false，可以阻止打开创建表单
- 没有return，则没有影响


```typescript
export function createFormClick (payload) {
	console.log('点击创建单据', payload)
  /**
  payload: {
  	instance: {id: 'mV05Lq4xfh', type: 'list-page-btn-create-form', controlType: 'base', props: CreateFormListButtonProperty, fieldType: undefined, …},
		options: {
  		createParams: {formId: 'form_7kd32y6zz3', appId: 'app_rsjuc9rb7y', sappId: 'sappId'},
			createQuery: {dataOrigin: 'sublist', relation_key: '', relation_uid: '', relation_map: '%7B%7D'}
   	},
		value: "list-page-btn-create-form"
  }
  */
  return false
}
```

<a id="uPb6W"></a>


#### payload参数：instance

当前组件的instance实例

<a id="QtjYI"></a>


#### payload参数：value

当前行数据

<a id="k4lIp"></a>


#### payload参数：options

- createParams 表单参数

- formId: 表单key
- appId: 应用id
- sappId: 菜单id

- createQuery URL参数

<a id="nhACt"></a>


### click-finish 点击完成时

<a id="GWl0h"></a>


#### 函数返回值

无


```typescript
export function clickFinish (payload) {
  console.log('执行完成事件', payload)
  /**
  payload: {
    instance: {id: 'mV05Lq4xfh', type: 'list-page-btn-create-form', controlType: 'base', props: CreateFormListButtonProperty, fieldType: undefined, …},
		options: {
  		opener: <Window>
    },
		value: "list-page-btn-create-form"
  }
  */
}
```

<a id="GUV6n"></a>


#### payload参数：instance

当前组件的instance实例

<a id="yVD9E"></a>


#### payload参数：value

固定值："list-page-btn-create-form"

<a id="xDOPQ"></a>


#### payload参数：options

- opener 只有是新窗口打开时，会返回打开window的对象
