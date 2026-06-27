---
title: "Number 数字"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/cgf91xlycpyabt8r"
visible: true
slug: "cgf91xlycpyabt8r"
doc_id: 187622029
updated_at: "2024-10-08T03:12:16.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Number 数字"
---
<a id="EYcLw"></a>


## 1.功能

<a id="zaBoV"></a>


## 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| defaultValue | number | '' | 默认值 | '' |
| isShowUnit | boolean | 是否勾选单位 | false |
| micrometer | boolean | 千分位展示 | false |
| numberType | 'number' | 'percentage' | 类型 （数值/百分比） | 'number' |
| percentageFormat | boolean | 百分比格式化 | false |
| precision | number | '' | 小数位数 | '' |
| rangeMax | number | '' | 最大值 | '' |
| rangeMin | number | '' | 最小值 | '' |
| regularRules | [RegularRules](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#oM2AX) | 正则校验 |  |
| showUpperCase | boolean | 显示大写数字 | false |
| unit | string | 自定义单位 | '' |
| unitPosition | 'left' | 'right' | 单位位置 left right | 'right' |

<a id="mTuPS"></a>


## 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#oM2AX)

<a id="bCFyx"></a>


## 4.事件

<a id="qRkTc"></a>


### 4.1. change 值变化时


```typescript
// 值变化时事件 示例
export function valueChange (payload) {
  console.log('值改变',payload)
}
// payload
{
    "instance": {
        ...
    },
    "value": 12312,
    "options": {
        "oldValue": 123
    }
}
```

<a id="lYDlH"></a>


### 4.2. input 用户输入时


```typescript
// 用户输入事件 示例
export function userInput (payload) {
  console.log('用户输入',payload)
}
// payload 示例
{
    "instance": {
        ...
    },
    "value": "12"
}
```

<a id="kGUed"></a>


### 4.3. focus 获取焦点时


```typescript
// 获得焦点事件 示例
export function getFocus (payload) {
  console.log('获得焦点',payload)
}
// payload 示例
{
    "instance": {
        ...
    },
    "value": "12"
}
```

<a id="hWAZ1"></a>


### 4.4. blur 失去焦点时


```typescript
// 失去焦点事件 示例
export function lostFocus (payload) {
  console.log('失去焦点',payload)
}
// payload 示例
{
    "instance": {
        ...
    },
    "value": "123"
}
```
