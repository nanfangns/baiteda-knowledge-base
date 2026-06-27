---
title: "Button 按钮"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/zlh5p6btn60glgi0"
visible: true
slug: "zlh5p6btn60glgi0"
doc_id: 187622009
updated_at: "2024-10-10T02:04:01.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "基础组件"
  - "Button 按钮"
---
<a id="EYcLw"></a>


## 功能

<a id="zaBoV"></a>


## 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| content | string | 按钮标题 | ​ |
| buttonType | 'primary' | 'secondary' | 'text' | 按钮类型 | 'primary' |
| showType | 'text' | 'icon' | 'iconText' | 显示形式 | ​ |
| color | 'primary' | 'danger' | 'warning' | 'success' | 'info' | 'blue' | 颜色 | 'primary' | |
| icon | string | 图标 |  |
| command | string | 按钮命令 |  |
| isLoading | boolean | 加载中 | false |
| optObj | [OptObject](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#VbRIB) | 操作项 | {} |

<a id="BGkDh"></a>


## 相关属性


[公共属性定义](../003-公共属性定义.md#bOazn)


[公共类型定义](../002-公共类型定义.md#VbRIB)

<a id="MjWKw"></a>


## 事件

<a id="NHvT6"></a>


### click 点击时


```typescript
export function click (payload) {
  console.log('click',payload)
}
// payload
{
    "instance": {
        ...
    },
    "value": ""
}
```

<a id="GBntd"></a>


## ​
