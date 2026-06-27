---
title: "Department 部门/行政组织"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/oe97hmh5hbzzkq41"
visible: true
slug: "oe97hmh5hbzzkq41"
doc_id: 187622024
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Department 部门/行政组织"
---
<a id="WdhaZ"></a>


# 1.功能

<a id="o72a2"></a>


# 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| multiple | boolean | 允许多选 | false |
| showType | "default"|"tree" | 树形结构 | tree |
| displayLevel | number | 行政组织层级 | 1 |
| defaultValue | string[] | 默认值 |  |
| defaultValueType | "current"|  "current\_dept\_id"|  "assigned"|  "fx"|  "none" | 默认值类型  "none"：无  "current"：当前登陆人行政组织  "current\_dept\_id"：当前登陆人所选择行政组织  "assigned"：指定行政组织  "fx"： 表达式 | "none" |

<a id="mtz0P"></a>


# 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF)

<a id="qhHio"></a>


# 4.事件

<a id="aVZ1y"></a>


## 4.1change 值变化时


```javascript
// 值变化事件 示例
export function valueChange (payload) {
  console.log('值发生变化时',payload)
}
// payload示例
{
    "instance": {
        ...
    },
    "value": [
        "bb555b5b7g35e2g1"
    ],
    "options": {
        "oldValue": [
            "test7"
        ]
    }
}
```

<a id="u6i1s"></a>


## 4.2focus 获取焦点时


```javascript
// 获得焦点事件 示例
export function getFocus (payload) {
  console.log('获得焦点时',payload)
}
// payload示例
{
    "instance": {
        ...
    },
    "value": {
    }
}
```

<a id="G566d"></a>


## 4.3blur 失去焦点时


```javascript
// 失去焦点事件 示例
export function lostFocus (payload) {
  console.log('失去焦点时',payload)
}
// payload示例
{
    "instance": {
        ...
    },
    "value": [
        "bb555b5b7g35e2g1"
    ]
}
```
