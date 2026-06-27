---
title: "JS 取值、赋值操作"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/ovrovybkll5wq2m2"
visible: true
slug: "ovrovybkll5wq2m2"
doc_id: 188000976
updated_at: "2025-10-27T09:09:47.000Z"
breadcrumb:
  - "百特搭大讲堂"
  - "表单进阶"
  - "JS 取值、赋值操作"
---
<a id="LCZZC"></a>


## 关键字

控件取值、控件赋值

<a id="sItBF"></a>


## 概述

二开里控件的取、赋值操作，针对不用的控件，有不同的取值、复制操作

<a id="vyDhK"></a>


## 表单控件

<a id="lMvG3"></a>


### 运行代码的环境


```typescript
const ctx = exports.ctx;
const utils = exports.utils;
const http = utils.getHttp()
const isMobile = utils.getDevice() === 'mobile'

const moment = exports.env.moment	//解决JS日期格式化和计算问题
const decimal = exports.env.decimal	//解决JS小数精度计算问题

export function init (payload) {
  //TODO: 以下示例代码在这里执行
}
```

<a id="fQBwx"></a>


### 数据类型划分

<a id="ScCFG"></a>


#### 短文本 varchar、长文本 text

值范围：任意字符串

适配控件：单行文本、下拉单选、单选、关联单选、多行文本、富文本

- 取值


```typescript
let fieldValue = ctx.getField('fm_takeout_relation', 'source_material_name')
console.log('输出 fieldValue:', fieldValue)
/**
输出fieldValue: '一个文本字符串'
*/
```


```typescript
let ctlValue = ctx.getState('wYySpq3gxY')
console.log('输出 ctlValue:', ctlValue)
/**
输出fieldValue: '一个文本字符串'
*/
```


```typescript
//值变化事件
export async function onchange (payload) {
  let ctlInst = payload.instance
  let ctlValue = payload.value
  const display = await utils.getCacheDisplay(ctlInst);

  let ctl_1_Inst = ctx.getInstance('GDtM9qQp4V')
  let ctl_1_Value = ctx.getState('GDtM9qQp4V')
  const display1 = await utils.getCacheDisplay(ctl_1_Inst);
  console.log('display:', display, '|', 'value:', ctlValue)
  console.log('display:', display1, '|', 'value:', ctl_1_Value)
}
/*
display: ['书本'] | value: 2445175e4d3a421599dda6a8492fe707
display: ['正常'] | value: 0
*/
```


- 存值


```typescript
ctx.setField('fm_takeout_relation', 'source_material_id', '新的值')
```


```typescript
ctx.setState('wYySpq3gxY', '新的值')
```


```typescript
ctx.setState('wYySpq3gxY', `1、第一段文字
2、第二段文字
3、第三段文字`)
```


技巧：可以使用模版字符串 `` 代替 ''，内容可以换行

- 清空


```typescript
ctx.setField('fm_takeout_relation', 'source_material_id', undefined)
```


```typescript
ctx.setState('控件的唯一标识符', undefined)
```

<a id="qWOHr"></a>


#### 数组 array

取值范围：数组字符串 ['', '', '' ...]

适配控件：下拉多选、多选

- 取值


```typescript
let fieldValue = ctx.getField('fm_takeout_relation', 'source_materials')
console.log('输出 fieldValue:', fieldValue)
/**
输出fieldValue: ['HCDDB202402270001', 'HCDDB202402270002', 'HCDDB202402270003']
*/
```


```typescript
let ctlValue = ctx.getState('wYySpq3gxY')
console.log('输出 ctlValue:', ctlValue)
/**
输出fieldValue: ['HCDDB202402270001', 'HCDDB202402270002', 'HCDDB202402270003']
*/
```


```typescript
//值变化事件
export async function onchange (payload) {
  let ctlInst = payload.instance
  let ctlValue = payload.value
  const display = await utils.getCacheDisplay(ctlInst);

  let ctl_1_Inst = ctx.getInstance('GDtM9qQp4V')
  let ctl_1_Value = ctx.getState('GDtM9qQp4V')
  const display1 = await utils.getCacheDisplay(ctl_1_Inst);
  console.log('display:', display, '|', 'value:', ctlValue)
  console.log('display:', display1, '|', 'value:', ctl_1_Value)
}
/*
display: ['书本','茶杯'] | value: ['84e16d38eb2341c981648bc0ea40706b','2445175e4d3a421599dda6a8492fe707']
display: ['正常', '启用'] | value: [0, 1]
*/
```


- 存值


```typescript
ctx.setField('fm_takeout_relation', 'source_materials', ['HCDDB202402270001', 'HCDDB202402270002'])
```


```typescript
ctx.setState('8ju86f673mtp7iq', ['HCDDB202402270001', 'HCDDB202402270002'])
```


- 清空


```typescript
ctx.setField('fm_takeout_relation', 'source_materials', [])
```


```typescript
ctx.setState('控件的唯一标识符', [])
```

<a id="aHsfL"></a>


#### 数值 decimal、日期 timestamp、整数 bigInt

取值范围：9007199254740991 ～ -9007199254740991。

适配控件：数字、评分、日期

- 取值


```typescript
let fieldValue = ctx.getField('fm_takeout_relation', 'source_deal_dt')
console.log('输出 fieldValue:', fieldValue, moment(fieldValue).format('YYYY-MM-DD hh:mm:ss'))
/**
输出fieldValue: 1708993615000, '2024-02-27 08:26:55'
*/
```


```typescript
let ctlValue = ctx.getState('wYySpq3gxY')
console.log('输出 ctlValue:', ctlValue, moment(fieldValue).format('YYYY-MM-DD'))
/**
输出fieldValue: 1708993615000, '2024-02-27'
*/
```


[Moment.js | format函数](http://momentjs.cn/docs/#/displaying/format/)

- 存值


```typescript
const newDate = moment('2024-02-24').valueOf()
ctx.setField('fm_takeout_relation', 'source_materials', newDate)
```


```typescript
const newDate = moment('2024-02-24').valueOf()
ctx.setState('8ju86f673mtp7iq', newDate)
```


```typescript
export function onload (payload) {
  const err_0_3 = 0.1 + 0.2
  const err_0_1 = 0.3 - 0.2
  console.log('err:', err_0_3, err_0_1)

  const res_0_3 = new decimal(0.1+ 0.2).toFixed(2);
  const res_0_1 = decimal.sub(0.3, 0.1).toNumber();
  console.log('result:',res_0_3, res_0_1)
}

/**
err: 0.30000000000000004 0.09999999999999998
result: 0.30 0.2
*/
```


[decimal.js API](http://mikemcl.github.io/decimal.js/)

- 清空


```typescript
ctx.setField('fm_takeout_relation', 'source_materials', undefined)
```


```typescript
ctx.setState('控件的唯一标识符', undefined)
```

<a id="Ksqs8"></a>


#### 人员 people、部门/组织 department

取值范围：字符串数组，如：['1857852475160152064']。单选/多选 都是数组

适配控件：人员、部门

- 取值


```typescript
let fieldValue = ctx.getField('fm_takeout_relation', 'sys_audit_user')
console.log('输出 fieldValue:', fieldValue)
/**
输出fieldValue: ['1857852475160152064']
*/
```


```typescript
let ctlValue = ctx.getState('wYySpq3gxY')
console.log('输出 ctlValue:', ctlValue)
/**
输出fieldValue: ['1857852475160152064']
*/
```


```typescript
export async function onuserchange (payload) {
  let userInst = payload.instance
  let userValue = payload.value
  const userDisplay = await utils.getCacheDisplay(userInst);

  let deptInst = ctx.getInstance('FfeXNi2JNg')
  let deptValue = ctx.getState('FfeXNi2JNg')
  const deptDisplay = await utils.getCacheDisplay(deptInst);
  console.log('人员:', userValue, '|', 'display:', userDisplay)
  console.log('部门:', deptValue, '|', 'display:', deptDisplay)
}
/*
人员: ["1857852475160152064"] | display: [{
    "employee_card": "2024015265",
    "id": 1857852475160152000,
    "join_date": null,
    "telephone": null,
    "employee_type": 1,
    "phone": "18272607984",
    "org_id": "1",
    "employee_id": "1857852475160152064",
    "gender": 1,
    "leader_id": "0",
    "uid": "1857852475160152064",
    "email": "2353023011@qq.com",
    "address": null,
    "org_type": null,
    "dept_name": "部门名称",
    "employee_name": "人员姓名",
    "dept_id": "1489016475015449600",
    "department_name": "部门名称"
}]
部门: ['1489016475015449600'] | display: [{
    "department_id": "1489016475015449600",
    "leader_name": "部门领导姓名",
    "department_name": "部门名称",
    "leader_id": "1489066892302747648",
    "id": 1489016475015449600,
    "parent_department_id": "1489016473262230528",
    "order": 1,
    "department_en_name": null,
    "org_type": "INTERNAL",
    "dept_tag": 1,
    "label_name": "行政",
    "display_value": "部门名称",
}]
*/
```


- 存值


```typescript
ctx.setField('fm_takeout_relation', 'sys_audit_user', ['1489061885880830976'])
```


```typescript
ctx.setState('wYySpq3gxY', ['1489061885880830976'])
```


- 清空


```typescript
ctx.setField('fm_takeout_relation', 'sys_audit_user', [])
```


```typescript
ctx.setState('控件的唯一标识符', [])
```

<a id="QxAIp"></a>


#### 附件 file、图片 image

取值范围：字符串数组，如：['507342961f9b4994afb014b705af0f75']。总是数组格式

适配控件：附件、图片

- 取值


```typescript
let fieldValue = ctx.getField('fm_takeout_relation', 'file')
console.log('输出 fieldValue:', fieldValue)
/**
输出fieldValue: ['507342961f9b4994afb014b705af0f75']
*/
```


```typescript
let ctlValue = ctx.getState('wYySpq3gxY')
console.log('输出 ctlValue:', ctlValue)
/**
输出fieldValue: ['507342961f9b4994afb014b705af0f75']
*/
```


```typescript
//值变化时
export async function onAttChange (payload) {
  let fileInst = payload.instance
  let fileValue = payload.value
  const fileDisplay = await utils.getCacheDisplay(fileInst);

  let picInst = ctx.getInstance('KGrKCLKv8t')
  let picValue = ctx.getState('KGrKCLKv8t')
  const picDisplay = await utils.getCacheDisplay(picInst);

  console.log('file:', fileValue, '|', 'display:', fileDisplay)
  console.log('pic:', picValue, '|', 'display:', picDisplay)
}
/*
file: ['507342961f9b4994afb014b705af0f75'] | display: [{
    "file_id": "507342961f9b4994afb014b705af0f75",
    "file_name": "企业微信20231124-173314@2x (1).png",
    "file_path": "/attach/attachment/serverpath/企业微信20231124-1733142x1.png",
    "file_size": 269346,
    "support_online_view": true,
    "online_view_url": "/attachment/api/v1/private/getOnlineViewPath?fileType=png&fileId=507342961f9b4994afb014b705af0f75&preview=true",
    "download_url": "//domain/attachment/api/v1/private/download/507342961f9b4994afb014b705af0f75",
    "del_file_url": "/attachment/api/v1/private/del?fileId=507342961f9b4994afb014b705af0f75",
    "creator": { ... },
    "create_time": 1710055944473
}]

pic: ['2c8d9ef0194e4139831158f899a4e587'] | display: [{
    "file_id": "2c8d9ef0194e4139831158f899a4e587",
    "file_name": "企业微信20231124-173314@2x (1).png",
    "file_path": "/attach/image/serverpath/企业微信20231124-1733142x1.png",
    "origin_url": "/attachment/api/v1/private/getOnlineViewPath?fileType=png&fileId=2c8d9ef0194e4139831158f899a4e587&preview=true",
    "thumb_url": "/attachment/api/v1/private/getThumbnailUrl?fileType=png&fileId=2c8d9ef0194e4139831158f899a4e587",
    "create_time": 1710056917000,
    "creator": { ... },
    "del_file_url": "/attachment/api/v1/private/del?fileId=2c8d9ef0194e4139831158f899a4e587",
    "download_url": "//domain/attachment/api/v1/private/download/2c8d9ef0194e4139831158f899a4e587"
}]
*/
```


- 存值


```typescript
ctx.setField('fm_takeout_relation', 'sys_audit_user', ['1489061885880830976'])
```


```typescript
ctx.setState('wYySpq3gxY', ['1489061885880830976'])
```


- 清空


```typescript
ctx.setField('fm_takeout_relation', 'sys_audit_user', [])
```


```typescript
ctx.setState('控件的唯一标识符', [])
```

<a id="Dm6oA"></a>


### 特殊控件

<a id="LXEhy"></a>


#### 日期区间 timescope

- 取值


```typescript
let fieldValue = ctx.getField('zz_model_cs', 'create_time')
const start = moment(Number(value[0])).format('YYYY-MM-DD hh:mm:ss')
const end = moment(Number(value[1])).format('YYYY-MM-DD')
console.log(value, start, end)
/**
输出fieldValue: ['1708876800000', '1714924799000'] '2024-02-26 12:00:00' '2024-05-05'
*/
```


```typescript
let ctlValue = ctx.getState('BI3FV3DyFy')
const start = moment(Number(value[0])).format('YYYY-MM-DD hh:mm:ss')
const end = moment(Number(value[1])).format('YYYY-MM-DD')
console.log(value, start, end)
/**
输出fieldValue: ['1708876800000', '1714924799000'] '2024-02-26 12:00:00' '2024-05-05'
*/
```


- 存值


```typescript
const start_dt = moment("2023-5-11").valueOf()
const end_dt = moment("2023-5-14").valueOf()
ctx.setField('zz_model_cs', 'create_time', [start_dt, end_dt])
```


```typescript
const start_dt = moment("2023-5-11").valueOf()
const end_dt = moment("2023-5-14").valueOf()
ctx.setState('BI3FV3DyFy', [start_dt, end_dt])
```


[Moment.js | format函数](http://momentjs.cn/docs/#/displaying/format/)

moment在顶部上下文环境中有定义

- 清空


```typescript
ctx.setField('zz_model_cs', 'create_time', [])
```


```typescript
ctx.setState('控件的唯一标识符', [])
```

<a id="jtwgm"></a>


#### 金额控件 currency

- 取值


```typescript
const fieldAmountValue = ctx.getField('zz_model_cs', 'field_amount')
const fieldCurrencyValue = ctx.getField('zz_model_cs', 'field_currency')
console.log('amount:', fieldAmountValue, '|', 'currency:', fieldCurrencyValue)

/*
amount: 199 | currency: 'CNY'
*/
```


```typescript
const value = ctx.getState('JhNpV8Knog')
console.log(value)
/*
{
    "amount": 199,
    "currency": "CNY"
}
*/
```


- 存值


```typescript
// 给金额组件赋值
ctx.setState('JhNpV8Knog', { amount: 100, currency: 'CNY' })

// 只需要改金额，不更改币种
// 方法一
ctx.getState('JhNpV8Knog').amount = 100

// 方法二
const state = ctx.getState('JhNpV8Knog')
state.amount = 100
ctx.setState('JhNpV8Knog', state)
```


```typescript
// 方法一
ctx.getState('JhNpV8Knog').amount = 100

// 方法二
const state = ctx.getState('JhNpV8Knog')
state.amount = 100
ctx.setState('JhNpV8Knog', state)
```


- 清空


```typescript
ctx.setField('zz_model_cs', 'amount', undefined)
ctx.setField('zz_model_cs', 'currency', 'CNY')
```


```typescript
ctx.setState('控件的唯一标识符', {"amount": undefined, "currency": "CNY"})
```

<a id="St08W"></a>


#### 计算公式 calc

- 取值


```typescript
const fieldAmountValue = ctx.getField('zz_model_cs', 'calc_amount')
console.log('amount:', fieldAmountValue)
/*
amount: 1990
*/
```


```typescript
const calc = ctx.getState('NaEKKJ6yDM')
console.log(calc)
/*
{
    "result": 1990,
    "unit": "万元"
}
*/
```


- 存值


```typescript
ctx.setField('zz_model_cs', 'calc_amount', 999)
```


```typescript
ctx.setState('NaEKKJ6yDM', {result: 999, unit: '万元'})
```


- 清空


```typescript
ctx.setField('zz_model_cs', 'calc_amount', undefined)
```


```typescript
ctx.setState('NaEKKJ6yDM', {result: undefined, unit: ''})
```

<a id="dHx8G"></a>


#### 地址 address

取值范围：JSON 格式对象

适配组件：地址

- 取值


```typescript
const fieldAddressValue = ctx.getField('zz_model_cs', 'address')
console.log(fieldAddressValue)
/*
{
    "city": "140300",
    "cityDisplay": "阳泉市",
    "district": "140321",
    "districtDisplay": "平定县",
    "province": "140000",
    "provinceDisplay": "山西省"
}
*/
```


```typescript
const controlAddressValue = ctx.getState('CSQcCy19fh')
console.log(controlAddressValue)
/*
{
    "city": "140300",
    "cityDisplay": "阳泉市",
    "district": "140321",
    "districtDisplay": "平定县",
    "province": "140000",
    "provinceDisplay": "山西省"
}
*/
```


- 存值


```typescript
ctx.setField('zz_model_cs', 'address', {
    "city": "140300",
    "cityDisplay": "阳泉市",
    "district": "140321",
    "districtDisplay": "平定县",
    "province": "140000",
    "provinceDisplay": "山西省"
})
```


```typescript
ctx.setState('CSQcCy19fh', {
    "city": "140300",
    "cityDisplay": "阳泉市",
    "district": "140321",
    "districtDisplay": "平定县",
    "province": "140000",
    "provinceDisplay": "山西省"
})
```


- 清空


```typescript
ctx.setField('zz_model_cs', 'address', undefined)
```


```typescript
ctx.setState('CSQcCy19fh', {result: undefined, unit: ''})
```

<a id="GXBZ2"></a>


## 明细表（待完善）

<a id="PcaiK"></a>


### 单行增/删

- 取行


```typescript
ctx.getField('数据源的code')[0]
// { /*行对象*/ }
```


```typescript
ctx.getState('明细子表唯一标识符')[0]
// { /*行对象*/ }
```


- 增行


```typescript
// 通过buildFields结合getField修改明细表数据
const newRow = ctx.buildFields('明细表的dataCode', { fieldCode: '值', fieldCode2: '值2' })
ctx.getField('明细表的dataCode').push(newRow)
```


```typescript
// 给明细表添加一个空行
// 需要注意，emptyRow不能被重复使用，只能使用一次，需要添加第二行就再执行一次getEmptyState
const emptyRow = ctx.getEmptyState('明细子表的唯一标识符')
ctx.getState('明细子表的唯一标识符').push(emptyRow)

// 给明细表添加一条有数据的行
ctx.getState('明细子表的唯一标识符').push(/* 需要设置一整行的值，对象类型 */)
ctx.getState('8ju86f673mtp7iq').push({ tj7triaeoo83cc0: 3 })
```


- 删行


```typescript
// 给明细表删除一条数据
ctx.getState('8ju86f673mtp7iq').splice(0, 1) // 删除明细表第一条数据

// 除了push以外，还可以使用JavaScript中数组的splice，shift，unshift,pop这些API，对明细子表进行增加一行，删除一行等操作
```

<a id="RknxR"></a>


### 批量数据操作

- 取值


```typescript
const subtable = ctx.getField('dataCode')
console.log(subtable)
// [{ /*行对象*/ },{ /*行对象*/ },{ /*行对象*/ }]
```


```typescript
const subtable = ctx.getState('明细子表唯一标识符')
console.log(subtable)
// [{ /*行对象*/ },{ /*行对象*/ },{ /*行对象*/ }]
```


- 存值


```typescript

```


```typescript
// 给明细表批量赋值
ctx.setState('明细子表的唯一标识符', /* 需要设置的值，数组对象类型 */)
// 给明细表批量赋值，覆盖当前表数据
ctx.setState('8ju86f673mtp7iq', [{ tj7triaeoo83cc0: 1 }, { tj7triaeoo83cc0: 2 }])
```


- 清空


```typescript

```

<a id="mSdxI"></a>


### 行内控件赋值

- 取值


```typescript

```


```typescript
ctx.getState('控件唯一标识符', 0) //明细表中第一行的指定组件的值
ctx.getState('8ju86f673mtp7iq', 0)
```


- 存值


```typescript

```


```typescript
// 给明细表内的组件赋值
ctx.setState('控件的唯一标识符', /* 需要设置的值 */， /* 行下标 */)
ctx.setState('8ju86f673mtp7iq', '新的值', 0) //给明细表中的第一行的8ju86f673mtp7iq组件赋值
```


- 清空


```typescript
// 给明细表内的组件赋值
ctx.setState('控件的唯一标识符', /* 需要设置的值 */， /* 行下标 */)
ctx.setState('8ju86f673mtp7iq', undefined, 0) //给明细表中的第一行的8ju86f673mtp7iq组件赋值
```

<a id="OV8p6"></a>


## 列表（待完善）

- 取值


```typescript
const selectedRows = ctx.getState(gridTableid)
```


- 存值


```typescript
// 设置选中值
ctx.setState(gridTableid,{
	selectedRowKeys: ['数据主键']
})
// 清空列表选中值
ctx.setState(gridTableid,{})
ctx.setState(gridTableid,{
  selectedRowKeys:[],
  selectedRows:[],
  selectedAllRowDatas: [] // 选中行数据 注意： 主子表关联关系 选中一张，会返回多条。
})
```


- 清空


```typescript
ctx.setState(gridTableid, [])
```

## 下级条目

- [明细子表赋值](001-明细子表赋值.md)
- [日期计算](002-日期计算.md)
- [上传控件上传后拿到文件全路径](003-上传控件上传后拿到文件全路径.md)
- [动态给下拉单选/多选组件赋值下拉选项](004-动态给下拉单选 多选组件赋值下拉选项.md)
