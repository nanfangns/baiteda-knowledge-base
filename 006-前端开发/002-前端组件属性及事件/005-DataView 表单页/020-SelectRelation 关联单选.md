---
title: "SelectRelation 关联单选"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/erfl41qzdoi2k6qh"
visible: true
slug: "erfl41qzdoi2k6qh"
doc_id: 187622037
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "SelectRelation 关联单选"
---
<a id="EYcLw"></a>


# 1.功能

<a id="zaBoV"></a>


# 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| canViewForm | boolean | 查看详情 | false |
| datasourceBind | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 关联数据源 | ​ |
| defaultValue | string | 默认值 | '' |
| listPageBind | [ListBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#cAqX8) | 绑定列表页 | ​ |
| multistageFilling? | [MultistageFillingItem](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#cJVo9)[] | *(Optional)* 数据填充 | [] |
| openMultistageFilling | boolean | 数据填充-查看/编辑页面生效 | false |

<a id="LB99R"></a>


# 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#cAqX8)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#cJVo9)

<a id="MjWKw"></a>


# 4.事件

<a id="NHvT6"></a>


## 4.1change 值变化时


```typescript

```

<a id="GBntd"></a>


## 4.2modal-ok 弹窗确认时

<a id="HYuML"></a>


### 4.2.1函数返回值

- return false：阻止弹窗关闭
- 其他：正常关闭弹窗，并选中值（没有 return、 return true）


```typescript
export async function onSelected (payload) {
  utils.toast(JSON.stringify(payload))
  console.log(payload)
	/*
   参数结构：
   payload: {
     instance: {id: "iJwZ5exdzi", type: "select-relation", ...},
     value: {
       selectedRowKeys: ["e5817f0f58df4f36a76665e42d30b168"],
       selectedRows: [{uid: "e5817f0f58df4f36a76665e42d30b168", SF1: "A1", app_version: " ", ...}]
     }
   }
  */

  return false
}
```

<a id="uPb6W"></a>


### 4.2.2payload参数：instance

当前组件的instance实例

<a id="QtjYI"></a>


### 4.2.3payload参数：value

- selectedRowKeys：选择的唯一键

- 类型：string[]
- 示例：["e5817f0f58df4f36a76665e42d30b168"]

- selectedRows：选择的行数据

- 类型：any[]
- 示例：[{uid: "e5817f0f58df4f36a76665e42d30b168", SF1: "A1", app\_version: " ", ...}]

<a id="azrBl"></a>


## 4.3focus 获取焦点时


```typescript

```

<a id="evacl"></a>


## 4.4blur 失去焦点时


```typescript

```
