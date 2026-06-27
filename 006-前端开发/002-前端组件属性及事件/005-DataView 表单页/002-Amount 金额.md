---
title: "Amount 金额"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/swldf7c272vk0ggc"
visible: true
slug: "swldf7c272vk0ggc"
doc_id: 187622016
updated_at: "2024-10-10T01:40:48.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Amount 金额"
---
<a id="EYcLw"></a>


## 功能

<a id="zaBoV"></a>


## 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| dataBind | [AmountDataBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#JifRO) | 金额和币种的数据绑定 |  |
| datasourceBind | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 币种的数据源绑定 |  |
| defaultValue | [AmountValue](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#qJsri) | 默认值 |  |
| micrometer | boolean | 千分位展示 | false |
| optionConfig | 'custom' | 'datasource' | 选项配置 custom datasource | 'datasource' |
| options | [OptionSetting](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#xt6xr)[] | 币种的默认选项 | [] |
| precision | number | '' | 小数位数 | '' |
| rangeMax | number | '' | 最大值 | '' |
| rangeMin | number | '' | 最小值 | '' |
| showUpperCase | boolean | 是否显示大写数字 | false |
| submitSelectCurrency | boolean | 提交时选择币种 | false |

<a id="AyAZG"></a>


## 相关属性


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#JifRO)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#qJsri)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#xt6xr)

<a id="dJsc0"></a>


## 事件

<a id="aVZ1y"></a>


### change 值变化时


```javascript
// 值变化时 事件示例
export function valueChange(payload) {
  console.log('值变化时', payload)
}

// payload 示例
{
    "instance": {
        ...
    },
    "value": {
        "amount": 123,
        "currency": "CNY"
    },
    "options": {
        "oldValue": {
            "amount": "",
            "currency": "CNY"
        }
    }
}
```

<a id="Ig9lh"></a>


### focus 获取焦点时


```javascript
// 获取焦点时 事件示例
export function getFocus(payload) {
  console.log('获取焦点时', payload)
}

// payload 示例
{
    "instance": {
        ...
    },
    "value": {
        "amount": "",
        "currency": "CNY"
    }
}
```

<a id="G566d"></a>


### blur 失去焦点时


```javascript
// 失去焦点时 事件示例
export function lostFocus(payload) {
  console.log('失去焦点时', payload)
}

// payload 示例
{
    "instance": {
        ...
    },
    "value": {
        "amount": "",
        "currency": "CNY"
    }
}
```

<a id="MLrgV"></a>


### Input 用户输入时


```javascript
// 用户输入时 事件示例
export function userInput(payload) {
  console.log('用户输入时', payload)
}

// payload 示例
{
    "instance": {
        ...
    },
    "value": "1"   // 值为用户输入后的控件值
}
```
