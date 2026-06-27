---
title: "Address 地址"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/zxrzzgszxuaohge8"
visible: true
slug: "zxrzzgszxuaohge8"
doc_id: 187622013
updated_at: "2024-10-10T01:40:02.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
  - "Address 地址"
---
<a id="zlJs9"></a>


## 功能

<a id="FDga3"></a>


## 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| addressType | ['province', 'city'?, 'district'?] | 地址类型 | ['province', 'city', 'district'] |
| defaultValue | [AddressValue](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#C9mc6) | 默认值 |  |
| defaultValueType | 'default' | 'current' | 默认值类型  default固定地址  current当前定位 | 'default' |

<a id="N9fa5"></a>


## 相关属性


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#bOazn)


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)


[公共类型定义](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#C9mc6)

<a id="COD67"></a>


## 事件

<a id="aVZ1y"></a>


### change 值变化时


```javascript
// 值变化事件示例
export function valueChange (payload) {
  console.log('值变化时',payload)
}

//  payload示例
{
  "instance": {
      ...
  },
  "value": {
      "city": "110100",
      "cityDisplay": "北京市",
      "district": "110101",
      "districtDisplay": "东城区",
      "province": "110000",
      "provinceDisplay": "北京"
  },
  "options": {
      "oldValue": {
          "city": "",
          "cityDisplay": "",
          "district": "",
          "districtDisplay": "",
          "province": "",
          "provinceDisplay": ""
      }
  }
}
```

<a id="Q0Dqc"></a>


### focus 获取焦点时


```javascript
// 获取焦点时 事件示例
export function getFocus (payload) {
  console.log('获取焦点时',payload)
}

//  payload示例
{
    "instance": {
        ...
    },
    "value": {
        "city": "",
        "cityDisplay": "",
        "district": "",
        "districtDisplay": "",
        "province": "",
        "provinceDisplay": ""
    }
}
```

<a id="G566d"></a>


### blur 失去焦点时


```javascript
// 失去焦点时 事件示例
export function lostFocus (payload) {
  console.log('失去焦点时',payload)
}

//  payload示例
{
    "instance": {
        ...
    },
    "value": {
        "city": "",
        "cityDisplay": "",
        "district": "",
        "districtDisplay": "",
        "province": "",
        "provinceDisplay": ""
    }
}
```
