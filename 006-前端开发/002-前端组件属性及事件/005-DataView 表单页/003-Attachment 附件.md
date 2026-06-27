---
title: "Attachment 附件"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/nggp9cz30rtsdmza"
visible: true
slug: "nggp9cz30rtsdmza"
doc_id: 187622017
updated_at: "2024-10-10T01:41:34.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Attachment 附件"
---
<a id="mp2bh"></a>


## 功能

​

<a id="SGNh4"></a>


## 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| showType | 'default' | 'table' | 展现形式  'default': 标题式  'table': 列表式 | 'default' |
| resultShowType | 'simple' | 'table' | 已上传文件展现形式  'simple': 简洁  'table': 表格 | 'simple' |
| attachmentAccept | string[] | 格式限制 |  |
| maxLimit | number | 最大上传数量(可选范围0-10) | 10 |
| maxSize | number | 文件大小限制MB(可选范围0-1000.0) | 100.0 |
| defaultValue | string[] | 默认值(文件id) |  |

<a id="bsy2H"></a>


## 相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)

<a id="LdoIP"></a>


## 事件

<a id="lyYEi"></a>


### change 值变化事件


```javascript
// 值变化事件示例
export function valueChange (payload) {
  console.log('值发生变化时',payload)
}
// payload示例
{
    "instance": {
        ...
    },
    "value": [
        "22c5fef2da884fcfbda790aa9b8075c5"
    ],
    "options": {
        "oldValue": [
            "db857b70418040b5be7c046e37ae475e",
            "22c5fef2da884fcfbda790aa9b8075c5"
        ]
    }
}
```
