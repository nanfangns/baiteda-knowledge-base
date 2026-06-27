---
title: "Radio 单选"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/cwednfrzw69gt5us"
visible: true
slug: "cwednfrzw69gt5us"
doc_id: 187622031
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Radio 单选"
---
<a id="zp3Yp"></a>


# 1.功能

<a id="c2UU3"></a>


# 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| optionsFormat | "vertical"|"horizontal" | 选项布局  "horizontal": 横排 "vertical": 竖排 | "horizontal" |
| optionConfig | "custom" | "datasource"  ​ | 选项设置  custom:自定义  datasource:关联数据源 | custom |
| options | [CheckCustomOption](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#F6giw)[] | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 选项 | ​ |

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
        ....
    },
    "value": "选项一",
    "options": {
        "oldValue": "选项二"
    }
}
```

<a id="K7iA4"></a>


## 4.2 点击时


```javascript
// 点击时事件 示例
export function click (payload) {
  console.log('点击时',payload)
}
// payload示例
{
    "instance": {
        ...
    },
    "value": "选项二"
}
```
