---
title: "Image 图片"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/kc4vxc3gq4zw096z"
visible: true
slug: "kc4vxc3gq4zw096z"
doc_id: 187622028
updated_at: "2024-10-08T03:06:35.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Image 图片"
---
<a id="zlJs9"></a>


## 1.功能

<a id="FDga3"></a>


## 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| maxLimit | number | 最大上传数量(可选范围0-10) | 10 |
| defaultValue | string[] | 默认值(图片id) |  |

<a id="N9fa5"></a>


## 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)

<a id="COD67"></a>


## 4.事件

<a id="aVZ1y"></a>


### 4.1. change 值变化时


```javascript
// 值变化事件示例
export function valueChange (payload) {
  console.log('值变化时',payload)
}

//  payload示例
{
    "instance": {
        ...
    },
    "value": [],
    "options": {
        "oldValue": [
            "9d976dd476e44fe5ac6e221422b0aa27"
        ]
    }
}
```
