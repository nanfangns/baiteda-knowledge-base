---
title: "Calc 计算公式"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/my0dliqyh44gcodk"
visible: true
slug: "my0dliqyh44gcodk"
doc_id: 187622019
updated_at: "2024-10-13T07:32:14.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Calc 计算公式"
---
<a id="aqzFK"></a>


## 功能

<a id="kJdcs"></a>


## 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| dataBind | [CalcDataBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#qJsri) | 计算公式的数据绑定 |  |
| defaultValue | [CalcValue](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#GyJTR) | 默认值 |  |
| micrometer | boolean | 千分位展示 | false |
| precision | number | '' | 保留小数点后几位 | '' |
| scriptEcho | CalcScriptEchoItem[] | 辅助回显的表达式 | [] |
| scriptSrc | string | 解释执行的表达式源码 | '' |
| showUpperCase | boolean | 是否显示大写数字 | false |

<a id="eh1lL"></a>


## 相关属性


[公共属性定义](../003-公共属性定义.md#bOazn)


[公共属性定义](../003-公共属性定义.md#OOWuV)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#qJsri)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#GyJTR)

<a id="grEuQ"></a>


## 事件

<a id="aVZ1y"></a>


### change 值变化时


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
    "value": {
        "result": 1,
        "unit": ""
    },
    "options": {
        "oldValue": {
            "result": 0,
            "unit": ""
        }
    }
}
```


​
