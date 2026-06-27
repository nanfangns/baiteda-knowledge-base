---
title: "Employee 人员"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/sfreeehs2t1wtuh7"
visible: true
slug: "sfreeehs2t1wtuh7"
doc_id: 187622026
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Employee 人员"
---
<a id="WdhaZ"></a>


# 1.功能

<a id="o72a2"></a>


# 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| multiple | boolean | 允许人员多选 | false |
| datasourceType | "EXTERNAL"|"INTERNAL" | 人员来源  "EXTERNAL": 外部组织  "INTERNAL": 内部组织 |  |
| range | "assign"|"all" | 指定人员  "all"：公司全员  "aassign"：指定人员 | all |
| rangeOptions | string[] | 指定人员(指定人员为assign时可配置) |  |
| defaultValue | string[] | 默认值 |  |
| showType | "tree"|"default" | 树形结构 | default |

<a id="mtz0P"></a>


# 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)

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
        "77d68e53"
    ],
    "options": {
        "oldValue": []
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
    "value": [
        "77d68e53"
    ],
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
        "77d68e53"
    ],
}
```
