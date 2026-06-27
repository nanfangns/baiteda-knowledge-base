---
title: "SelectMultiple 下拉多选"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/ag2gwy6irubdsuob"
visible: true
slug: "ag2gwy6irubdsuob"
doc_id: 187622036
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "SelectMultiple 下拉多选"
---
<a id="zp3Yp"></a>


# 1.功能

<a id="c2UU3"></a>


# 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| type | 'checkbox' | 'select-multiple'  ​ | 类型  checkbox:多选  select-multiple:下拉多选 | checkbox |
| defaultShowOptions | Boolean | 默认展示选项 | true |
| optionConfig | "custom" | "datasource"  ​ | 选项设置  custom:自定义  datasource:关联数据源 | custom |
| options | [CheckboxCustomOption](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#F6giw)[] | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 选项 | ​ |

<a id="QIfGM"></a>


# 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF)

<a id="swV8E"></a>


# 4.事件

<a id="f4Tw3"></a>


## 4.1 值变化事件


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
        "选项二"
    ],
    "options": {
        "oldValue": []
    }
    "value": [
        "选项二"
    ]
}
```

<a id="xAI3a"></a>


## 4.2 获得焦点事件


```javascript
// 获得焦点事件 示例
export function getFocus (payload) {
  console.log('获得焦点',payload)
}
// payload示例
{
    "instance": {
        ...
    },
    "value": [
        "选项二"
    ]
}
```

<a id="dpyws"></a>


## 4.3 失去焦点事件


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
        "选项二"
    ]
}
```
