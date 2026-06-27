---
title: "DateRange 日期区间"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/sq0l04sc910ns0sy"
visible: true
slug: "sq0l04sc910ns0sy"
doc_id: 187622022
updated_at: "2024-10-08T03:16:50.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "DateRange 日期区间"
---
<a id="pKZA7"></a>


## 1.功能

​

<a id="dZPNR"></a>


## 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| dataBind | [RangeDataBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#FAD3j) | 数据绑定项 |  |
| dateType | [DateType](https://baiteda.yuque.com/staff-shgita/nbg92z/sruuxxqgq71679rg#GRsvi) | 日期格式 | 'date' |
| defaultValue | [RangeDateValue](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#wnCsp) | 默认值 |  |
| limitDateList | Array<LimitDate> | 日期限制范围 | [] |
| placeholderEnd | string | 日期区结束的提示文字 | '' |
| placeholderStart | string | 日期区间开始的提示文字 | '' |
| rangeMax | number | '' | 结束日期 | '' |
| rangeMin | number | '' | 开始日期 | '' |
| setValueType | 'custom' | 'now' | 日期默认值设置方式 | 'custom' |

<a id="JKdHq"></a>


## 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#FAD3j)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#wnCsp)


[公共枚举](https://baiteda.yuque.com/staff-shgita/nbg92z/sruuxxqgq71679rg#GRsvi)

<a id="qhHio"></a>


## 4.事件

<a id="aVZ1y"></a>


### 4.1. change 值变化时


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
      "min": "1722441600000",
      "max": "1723910399000"
  },
    "options": {
      "oldValue": {
          "min": "",
          "max": ""
      }
  }
}
```

<a id="u6i1s"></a>


### 4.2. focus 获取焦点时


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
        "1722493419900",
        "1723875819900"
    ]
}
```

<a id="G566d"></a>


### 4.3. blur 失去焦点时


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
        "1722493419900",
        "1723875819900"
    ]
}
```
