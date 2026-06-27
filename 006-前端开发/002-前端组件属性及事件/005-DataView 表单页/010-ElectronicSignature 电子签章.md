---
title: "ElectronicSignature 电子签章"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/dnudgkpvhbgdqpc3"
visible: true
slug: "dnudgkpvhbgdqpc3"
doc_id: 187622025
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "ElectronicSignature 电子签章"
---
<a id="mp2bh"></a>


# 1.功能

​

<a id="SGNh4"></a>


# 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| buttonType | "primary"|"secondary" | 按钮类型 | primary |
| color | "primary"|"blue"|... | 颜色 |  |
| signatureConfig | [signatureConfig](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#Rkmi1)[] | 签章设置 |  |

<a id="bsy2H"></a>


# 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)

<a id="LdoIP"></a>


# 4.事件

<a id="lyYEi"></a>


## 4.1 click 点击事件


```javascript
// 点击事件示例
export function click (payload) {
  console.log('点击时',payload)
}
// payload示例
{
    "instance": {
        ...
    },
    "value": ""
}
```
