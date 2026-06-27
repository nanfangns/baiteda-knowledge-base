---
title: "Score 评分"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/kgr5e9n0hvn710sf"
visible: true
slug: "kgr5e9n0hvn710sf"
doc_id: 187622039
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Score 评分"
---
<a id="EYcLw"></a>


# 1.功能

<a id="zaBoV"></a>


# 2.属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| totalScore | number | 总分（最大值100） | 5 |
| isShowExplain | boolean | 是否展示分数说明 | true |
| explain | [explainOption](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#WXS6t)[] | 分数说明 | ​ |
| scoreType | "praise"|"star"|"flower"|"hand"|"heart"|"smile" | 样式 | ​ |

<a id="mMATX"></a>


# 3.相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)

<a id="MjWKw"></a>


# 4.事件

<a id="NHvT6"></a>


## 4.1change 值变化时


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
    "value": 56,
    "options": {
        "oldValue": 0
    }
}
```

<a id="oIZb0"></a>


## 4.2click 点击时


```typescript
// 点击事件 示例
export function click (payload) {
  console.log('点击',payload)
}
// payload 示例
{
    "instance": {
        ...
    },
    "value": 56
}
```
