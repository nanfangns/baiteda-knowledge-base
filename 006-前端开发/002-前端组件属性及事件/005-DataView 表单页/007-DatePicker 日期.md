---
title: "DatePicker 日期"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/fy87n992gfyx7gcq"
visible: true
slug: "fy87n992gfyx7gcq"
doc_id: 187622021
updated_at: "2024-10-09T08:46:03.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "DatePicker 日期"
---
<a id="if08e"></a>


## 1.功能

<a id="qhczT"></a>


## 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| dateType | "year"|"month"|"date"|"datehour"|"datemin"|"datetime" | 日期类型  year: 年  month: 年-月  date: 年-月-日  datehour: 年-月-日 时  datemin: 年-月-日 时:分  datetime: 年-月-日 时:分:秒 | date |
| commonTimeSetting | ["yesterday"|  "today"|  "tomorrow"|  "lastWeek"|  "thisWeek"|  "lastMonth"|  "nextWeek"|  "nextMonth"|  "thisMonth"|  "lastYear"|  "thisYear"|  "nextYear"] | 常用时间设置  yesterday:昨天  today:今天  tomorrow:明天  lastWeek:上周  thisWeek:本周  nextWeek:下周  lastMonth:上月  thisMonth:本月  nextMonth:下月  lastYear:去年  thisYear:今年  nextYear:明年 | [] |
| limitDateList | [limitDateListOption](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#sLflJ)[] | 时间限制范围 |  |
| setValueType | "custom"|"now" | 日期默认值设置方式  custom：自定义  now： 当前时间 | custom |

<a id="h3CYM"></a>


## 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)

<a id="rNG70"></a>


## 4.事件

<a id="stSVp"></a>


### 4.1. 值变化事件


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
    "value": "1729231200000",
    "options": {
        "oldValue": "1722492000000"
    }
}
```

<a id="nBkNQ"></a>


### 4.2. 获得焦点事件


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
    "value": "1722492000000"
}
```

<a id="bhsL1"></a>


### 4.3. 失去焦点事件


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
    "value": "1729231200000"
}
```
