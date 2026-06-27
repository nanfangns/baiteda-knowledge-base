---
title: "Tree 树"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/ez8qp3ep6o63fiek"
visible: true
slug: "ez8qp3ep6o63fiek"
doc_id: 187622040
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Tree 树"
---
<a id="EYcLw"></a>


# 1.功能

<a id="zaBoV"></a>


# 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| multiple | boolean | 允许多选 | false |
| containsSubNode | boolean | 包含下级节点 | false |
| levelType | "top"|  "specified"|  "last" | 可选层级  "top"：全部节点  "specified"：指定节点  "last"：仅末级节点 | "top" |
| defaultCollapse | "top"|  "specified"|  "none" | 默认展开状态  "top"：全部节点  "specified"：指定节点  "last"：收起全部 | "top" |

<a id="mMATX"></a>


# 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF)

<a id="MjWKw"></a>


# 4.事件

<a id="NHvT6"></a>


## 4.1change 值变化时


```typescript
// 值变化时事件 示例
export function valueChange (payload) {
  console.log('值改变',payload)
}
// payload
{
    "instance": {
        ...
    },
    "value": [
        "37b539c1165c4757b1a02fab728340c8"
    ],
    "options": {
        "oldValue": [
            "9a4f779ea14c493fa58875222a31ca11"
        ]
    }
}
```

<a id="oIZb0"></a>


## 4.2click 点击时


```typescript
// 点击事件 示例
export function click (payload) {
  console.log('点击',payload)
}
// payload 示例
{
    "instance": {
      ...
    },
    "value": [
        "37b539c1165c4757b1a02fab728340c8"
    ]
}
```
