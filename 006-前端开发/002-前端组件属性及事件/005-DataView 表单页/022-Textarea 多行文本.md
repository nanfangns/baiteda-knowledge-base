---
title: "Textarea 多行文本"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/egqiwgl7kyshrysc"
visible: true
slug: "egqiwgl7kyshrysc"
doc_id: 187622038
updated_at: "2024-10-08T03:00:59.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Textarea 多行文本"
---
<a id="EYcLw"></a>


## 1.功能

<a id="zaBoV"></a>


## 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| defaultValue | string | 默认值 | '' |
| lineEllipsis | number | 行数设置 | 4 |
| maxLength | number | 最大长度 | 50000 |
| minLength | number | 最小长度 | 0 |

<a id="dXJJ6"></a>


## 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)

<a id="Cf0Yl"></a>


## 4.事件

<a id="cGqn0"></a>


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
    "value": "12312",
    "options": {
        "oldValue": "123"
    }
}
```

<a id="tsRPG"></a>


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

<a id="yKguh"></a>


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

<a id="gA8Zf"></a>


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
