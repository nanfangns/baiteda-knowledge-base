---
title: "DataView 表单页"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/kzz0mvkhag77wha9"
visible: true
slug: "kzz0mvkhag77wha9"
doc_id: 187622015
updated_at: "2024-10-11T06:00:56.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "DataView 表单页"
---
<a id="h86jv"></a>


# 功能

版本：4.0.0

<a id="qiBxJ"></a>


# 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| datasourceBind | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 数据高级设置 |  |
| isLoading | boolean | 加载中 | false |

<a id="kV9TF"></a>


# 事件

<a id="XXk12"></a>


## engine-initialized 页面加载前（5.2.0新增+）

**注:** 该事件阶段设置默认值只能设置绑定了 **“字段”** 的表单控件 ,如果设置未绑定字段的默认值需在 [**“页面加载时”**](#Jfh6r) 事件内 [setState](../../001-前端二开API.md#GRNtW) 设置默认值

表单的主表数据 和 明细表数据 组装完毕后，触发该事件 适用于 初始化处理控件默认值，防止页面值抖动/变化, 该事件赋默认值后不会触发值发生变化事件.


```javascript
// 注意 该阶段 instance 实例 并未初始化 并不能更改 对应控件属性 例如：显/隐 只读/编辑态
// payload.value 为引用对象 可直接更改
export function pageEventBefore (payload) {
    // payload 中有完整的主表 + 明细表的数据

    //  主表某个字段赋值 chakanzibiao 为主表code tip_detail   为字段code
    payload.value.chakanzibiao.tip_detail ='短文本是一个短文本字段'
    payload.value.chakanzibiao.employee_id = ['employee_id-demo1','employee_id-demo2']
    payload.value.chakanzibiao.employee_name = '百特搭课堂助手'

    // 	明细表整体赋值 carInfoDetail 为subCode
    payload.value.carInfoDetail = [ { car_no: 'XX-XXXXX',car_name: 'XXX-XXX' },{ car_no: 'XX-XXXXX',car_name: 'XXX-XXX' } ]
    // 明细表内 某行赋值
    payload.value.carInfoDetail[2] = { car_no: 'XX-XXXXX',car_name: 'XXX-XXX' }
    //明细表 某行 某个字段赋值
    payload.value.carInfoDetail[2].car_no = 'demo-xxxxx'
}
//支持同步执行
export function async pageEventBefore (payload) {
  const result = await utils.querySvc({
  	app_id: 'app_uqaucma53i',
  	query: {
  		page_index: 1,
  		page_size: 100,
  	},
  	svc_code: 'carinfo_detail_selectMore',
  })
  //result.data 值 为 [{ car_no: 'XX-XXXXX',car_name: 'XXX-XXX' },{ car_no: 'XX-XXXXX',car_name: 'XXX-XXX' },{ car_no: 'XX-XXXXX',car_name: 'XXX-XXX' },{ car_no: 'XX-XXXXX',car_name: 'XXX-XXX' }]
  //设置明细表默认值 carInfoDetail 为 subCode
   payload.value.carInfoDetail =  result.data
}
```

<a id="Jfh6r"></a>


## 3.2 engine-mounted 页面加载时

表单的主表数据 和 明细表数据全部准备完毕后，触发该事件


```javascript
export function onMounted (payload) {
  console.log(payload)
  // payload 中有完整的主表 + 明细表的数据
}
```


​

<a id="mj59D"></a>


## 3.3 engine-submit 表单提交前

点击保存/提交 后，表单通过了内置校验规则，触发该事件，通常用于表单数据的校验


```javascript
export function onSubmit (payload) {
  console.log(payload)
  // payload 中有当前流程提交相关参数
}

// return false则阻止继续提交
export function onSubmit (payload) {
  if (ctx.getState('xxx') !== 'xxx') {
     return false
  }
}
```


return false 或 js异常：

- 表单提交恢复到提交前状态。pc、移动端均停留在表单操作栏
- 审批操作恢复到点击前状态。pc、移动端均停留在审批操作框界面

用户可以再次提交

<a id="rvJJD"></a>


## 3.3 engine-submit-params 表单提交时 （2.2.10版本新增）

表单数据组装完成，即将调用后端服务。主要用于改变提交时的数据。

注意：

1、在此事件内通过 ctx api 修改表单页面的数据将不会影响传递给后端的数据

2、⚠️ 非新建的场景（修改、保存草稿、审批等）payload中获取的数据，明细表数据仅包含增量修改的数据，没有全量数据。

​


```javascript
export function onSubmitting (payload) {
  // payload.value 传递给后端服务的数据，可以通过修改data_set/subtable_data_set内的值，来达到修改保存数据的效果
}

// 只有 return 一个对象才会被使用，如果不return，则修改无效
export function onSubmitting (payload) {
  payload.value.xxx = 'xxx'
  return payload.value
}
```


⚠️ 注意：这个事件在流程审批场景下会调用两次：

第一次调用：计算下一步审批人的

第二次调用：流程真实审批

必须调用两遍，而且传值要一样，不然下一步审批人 和 真实审批 会出现不匹配的情况。

<a id="pohdE"></a>


## 3.4engine-submitted 表单提交后

表单已经做完数据保存、流程审批操作后，触发该事件


```javascript
export function onSubmitted (payload) {
  //payload.value 有后端返回的该记录的唯一编号
}

// return false则阻止页面关闭
export function onSubmitted (payload) {
  return false
}
```


return false 或 js异常：

- 表单提交保持提交后状态。pc、移动端均停留在表单操作栏
- 审批操作保持点击后状态。pc、移动端均停留在审批操作框界面，按钮处于loading状态

阻止用户再次提交

<a id="m9U8K"></a>


# 子组件


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OOWuV)

<a id="zTJcX"></a>


# 代码事件

<a id="ZrxA8"></a>


## 5.1 审批组件按钮点击（3.1.13版本增加）

由于该事件场景稍窄，不在设计器中配置，可以通过代码监听。

可以通过 return false 阻止审批组件按钮后续的操作


```typescript
const ctx = exports.ctx;
const utils = exports.utils;
const http = utils.getHttp()
const isMobile = utils.getDevice() === 'mobile'

ctx.on('approval:onBeforeBtnClick', (params) => {
  console.log(params)
  return false
})

// 点击 同意按钮-输出：
// {
//	 "instance": undefined,
//   "options":{
//     "button":{
//       "command_id":"general",
//       "command_type":"general",
//       "command_name":{"zh":"同意","en":"Approve","ja":"承認","locale":"同意"},
//       "custom":0,
//       "isShowTip":false
//     }
//   }
// }

// 点击 拒绝按钮-输出：
// {
//   "instance": undefined,
//   "options":{
//     "button":{
//       "command_id":"rollBackTaskByExpression",
//       "command_type":"rollBackTaskByExpression",
//       "command_name":{"zh":"拒绝","en":"Reject","ja":"却下","locale":"拒绝"},
//       "custom":0,
//       "isShowTip":false
//     }
//   }
// }
```

<a id="vm3xc"></a>


## 5.2 表单取消点击事件

return false可以阻止后续页面跳转，但是无法关闭弹窗


```typescript
export function onload (payload) {
  ctx.on('custom:formCancel', () => {
    // todo ...
    return false
  })
}
```

<a id="VwTmE"></a>


# ​

## 下级条目

- [Address 地址](001-Address 地址.md)
- [Amount 金额](002-Amount 金额.md)
- [Attachment 附件](003-Attachment 附件.md)
- [AutoNumber 自动编号](004-AutoNumber 自动编号.md)
- [Calc 计算公式](005-Calc 计算公式.md)
- [Checkbox 多选](006-Checkbox 多选.md)
- [DatePicker 日期](007-DatePicker 日期.md)
- [DateRange 日期区间](008-DateRange 日期区间.md)
- [Department 部门/行政组织](009-Department 部门 行政组织.md)
- [ElectronicSignature 电子签章](010-ElectronicSignature 电子签章.md)
- [Employee 人员](011-Employee 人员.md)
- [Image 图片](012-Image 图片.md)
- [Input 单行文本](013-Input 单行文本.md)
- [Number 数字](014-Number 数字.md)
- [OrganizationSelection 业务组织](015-OrganizationSelection 业务组织.md)
- [Radio 单选](016-Radio 单选.md)
- [RichText 富文本](017-RichText 富文本.md)
- [Select 下拉单选](018-Select 下拉单选.md)
- [SelectMultiple 下拉多选](019-SelectMultiple 下拉多选.md)
- [SelectRelation 关联单选](020-SelectRelation 关联单选.md)
- [Score 评分](021-Score 评分.md)
- [Textarea 多行文本](022-Textarea 多行文本.md)
- [Tree 树](023-Tree 树.md)
