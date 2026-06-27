---
title: "ListSelectButton 列表选择"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/syqocorl8tgdlq6g"
visible: true
slug: "syqocorl8tgdlq6g"
doc_id: 187622011
updated_at: "2024-10-10T02:07:42.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "基础组件"
  - "ListSelectButton 列表选择"
---
<a id="EYcLw"></a>


## 功能

<a id="zaBoV"></a>


## 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| fillBack | [FillBackBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#hLkNr) | 回填配置 | ​ |
| fillPayload | [FillPayloadBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#BXs1m) | 数据过滤 | ​ |
| listPageBind | [ListBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#cAqX8) | 绑定列表页 | ​ |

<a id="BGkDh"></a>


## 相关属性


[公共属性定义](../003-公共属性定义.md#bOazn)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#hLkNr)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#BXs1m)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#cAqX8)

<a id="MjWKw"></a>


## 事件

<a id="NHvT6"></a>


### click 点击时


```typescript

```

<a id="GBntd"></a>


### modal-ok 弹窗确认时

<a id="HYuML"></a>


#### 函数返回值

- return false：阻止弹窗关闭
- 其他：正常关闭弹窗，并填充（没有 return、 return true）


```typescript
export async function onConfirm (payload) {
  utils.toast(JSON.stringify(payload))
  console.log(payload)
	/*
   参数结构：
   payload: {
     instance: {id: "KoddpJvz3X", type: "list-select-button", ...},
     value: {
       selectedRowKeys: ["c92033f4268744cdbf159e68801add8b"],
       selectedRows: [{uid: "c92033f4268744cdbf159e68801add8b", SF4: '', SF3: '', SF5: '选项一', ...}]
     }
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

- selectedRowKeys：选择的唯一键

- 类型：string[]
- 示例：["e5817f0f58df4f36a76665e42d30b168"]

- selectedRows：选择的行数据

- 类型：any[]
- 示例：[{uid: "e5817f0f58df4f36a76665e42d30b168", SF4: '', SF3: '', SF5: '选项一', ...}]

<a id="azrBl"></a>


### click-finish 点击完成时


```typescript
export function finish_click (payload) {
  console.log('finish_click', payload)

  /*
  参数结构：
   payload: {
     instance: {id: "KoddpJvz3X", type: "list-select-button", ...},
     value: ["c92033f4268744cdbf159e68801add8b"],
     options: {
       selectedRows: [{uid: "e5817f0f58df4f36a76665e42d30b168", SF4: '', SF3: '', SF5: '选项一', ...}],
       subtableDiff: {add: ['fe08248a82ad473e90da3c9b92319f58'],remove:[]}
     }
   }
  */
}
```

<a id="wRkgb"></a>


#### payload参数：instance

当前组件的instance实例

<a id="IEDVl"></a>


#### payload参数：value

- 类型：string[]
- 示例：['2f7499ca5f7b4db2a61cd359c93c6309','4c34ace2a58c4b0c862ae3c3ab40fdf0','fe08248a82ad473e90da3c9b92319f58']

<a id="pfjGB"></a>


#### payload参数：options

- selectedRows：选择的行数据

- 类型：any[]
- 示例：[{uid: "e5817f0f58df4f36a76665e42d30b168", SF4: '', SF3: '', SF5: '选项一', ...}]

- subtableDiff：明细表选择后的差异值

- 类型：{add: string[], remove:string[]}
- 示例：{add: ['fe08248a82ad473e90da3c9b92319f58'],remove:[]}
