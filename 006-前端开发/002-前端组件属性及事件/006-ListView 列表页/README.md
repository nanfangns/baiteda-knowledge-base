---
title: "ListView 列表页"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/koaknk55flhsgub9"
visible: true
slug: "koaknk55flhsgub9"
doc_id: 187622041
updated_at: "2024-10-14T06:07:06.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "ListView 列表页"
---
<a id="Q3n9O"></a>


# 功能

版本：4.0.0

<a id="nFkgU"></a>


# 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| countType? | 'sync' | 'async' | 'none' | *(Optional)* 计数模式 | 'async' |
| datasourceBind | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 数据高级设置 |  |
| isAllLoaded | boolean | 加载全部数据 | true |
| isFixedHeader | boolean | 固定表头 | false |
| isLoading | boolean | 加载中 | false |
| isShowSubList | boolean | 显示明细表 | false |
| showFullScreen | boolean | 全屏显示 | false |
| sublistPage | SubListPageConfig | 抽屉内容配置 |  |
| triggerFieldCode | string | 触发字段 |  |
| triggerType | TriggerType | 触发时机 1=整行，2=字段 | 1 |

<a id="mGvMN"></a>


# 事件

<a id="A9qX5"></a>


## engine-initialized 页面加载前（5.2.0新增+）

**注:该事件只有页面初始化时会给控件赋默认值,后续更改查询条件不会触发该事件**

列表页面接口调用前触发 用于设置过滤条件 及 搜索区域默认值


```javascript
// 同步动作
export function listInitialized () {
   ctx.setState('唯一标识符','你想要设置的搜索区域控件默认值')
}
// 调用服务查询默认值,异步动作
export async function listInitialized () {
  const result  = await utils.querySvc({
        "app_id":"app_6qqhxqfg6g",
        "save_datas":{//添加、修改服务是调用，数据格式要对应上
           "ids":['xxx','xxx','xxx']
        },
        "svc_code":"get_select_more_data"
    })

  // 1. 对象结构:  result.data 结构为: { age:1 ,name:'测试姓名', custominfo:'示例信息' }
  // 推荐: key: 键值 value: 对应要赋默认值的控件id
  const searchControlMap = {
    'age':'X7yj4zWJAr',
    'name':'X7yj4zWJBr',
    'custominfo':'X7yj4zWJCr',
  }
  //  需根据定义数据结构来操作
  Object.keys(result.data).forEach(key=>{
   ctx.setState(searchControlMap[key],,result.data[key])
  })
  // 2. 数组结构 :  result.data 结构为: [1,'测试姓名','示例信息']
  // 推荐:
   const searchControlArr = ['X7yj4zWJAr','X7yj4zWJBr','X7yj4zWJCr']
    result.data.forEach((value, index)=>{
     ctx.setState(searchControlArr[index], value)
    })
  // 3. 或一个一个赋值
  //对象
  ctx.setState('唯一标识符',result.data.age)
  //数组
  ctx.setState('唯一标识符',result.data[0])
}
```

<a id="OaWin"></a>


## engine-mounted 页面加载时

列表页面初始化时触发，没有列表数据（异步加载）。


```typescript
export function onMounted (payload) {
  console.log(payload)
  //payload 中含有查询框中设置的默认值
}
```

<a id="VluyT"></a>


## list-search 列表数据查询构建时

**注: 查询构建时 事件内传递的参数 查询时或修改查询条件时都会带上,属于查询构建时默认值.**

列表的查询条件构建完成后调用该事件，可以在事件中修改查询条件等 [查询类型枚举](https://baiteda.yuque.com/staff-shgita/nbg92z/sruuxxqgq71679rg#TncFR)


```javascript
export function onListDataSearch (payload) {
  //请注意，由于payload.value里其他参数会在表格点击查询、排序时传递过来
  //不要给payload.value重新赋值，而是直接修改其参数
  payload.value.query = [{"key": "f1", "value": ["asdf"],"type": "LIKE","key_type": "varchar"}]
  payload.value.page.page_size = 40
  // 必须要return，不return则会使用默认查询条件
  return payload.value
}

// payload.value中对象格式如下
// {
//     "page": {
//         "page_index": 1,
//         "page_size": 20
//     },
//     "query": [
//        {"key": "f1", "value": ["asdf"],"type": "LIKE","key_type": "varchar"},
//        {"key": "f2","value": ["sadfasdf"],"type": "LIKE","key_type": "varchar"}
//     ],
//     "filters": [],
//     "orders": []
// }
```

<a id="RWv5Y"></a>


### 示例：改变操作列的宽度（在列表查询构建前，数据准备完成时，3.4.0新增）


```javascript
const ctx = exports.ctx;
const utils = exports.utils;
const http = utils.getHttp()
const isMobile = utils.getDevice() === 'mobile'
const headers = ctx.getInstance('jOuz95skoG').children.find(item => item.type === 'grid-table').props.headers
  headers.forEach(item => {
    if (item.type === "operation-column") {
      item.props.width = 600
    }
  })
```

<a id="ziULU"></a>


## list-mounted 列表数据返回时


```javascript
export function onQueryResponse (payload) {
  // payload.value 为当前列表的返回值
  console.log('返回结果', payload)
  const newResponse = payload.value
  // 必须要return，不return则会使用默认数据进行渲染
  return newResponse
}
```


注意：以下按钮操作事件，需要配置代码执行事件

<a id="NDtbN"></a>


## list-actions 点击操作按钮时

<a id="FySP2"></a>


### 触发时机

- 点击列表工具栏中的创建按钮
- 点击列表每行操作列上的按钮

- 查看
- 编辑
- 删除
- 自定义按钮

<a id="RwJNU"></a>


### 函数返回值

- return false 可以阻止操作行为
- return {key1:'value1'} ，打开的链接上additional\_query会拼接return出来的参数。如：/apps/desktop/process/app\_6qqhxqfg6g/sappId/test\_form\_gw8kwgg0g5/1ec4656b00ea431d83f2ac6445be7666?type=view&additional\_query={%22key1%22:value1}
- 没有return，则没有影响


```typescript
export async function onClickOperationButton (payload) {
  console.log(payload)
  //创建表单
  /**
  payload: {
    instance: {id: 'n4arbqNkf4', type: 'list-view', controlType: 'layout', props: ListViewControlProperty, fieldType: undefined, …},
		options: {
  		formId: 'form_7kd32y6zz3',
    	appId: 'app_rsjuc9rb7y',
     	sappId: 'sappId',
      dataOrigin: 'sublist',
      relation_key: '', …
    },
		value: {}
  }
  */
	//阻止 创建表单的按钮 点击
  if (payload.options.action === 'create') {
    return false
  }

  //查看按钮 / 编辑
  /**
  payload: {
    instance: { ... },
    options:{
      actionCode: "view",
      action: 'view',
      appId: "app_6qqhxqfg6g",
      formId: "test_form_gw8kwgg0g5",
      sappId: "sappId",
      uId: "1ec4656b00ea431d83f2ac6445be7666",
      record: { ... }
    },
    value: { ... }
  }
  */
  //阻止 编码为view的按钮 点击
  if (payload.options.actionCode === 'view') {
    return {
      query_param1: payload.value.uid
    }
  }


  //删除按钮
  /**
  payload: {
    instance: { ... },
    options:{
      actionCode: "delete",
      action: 'delete',
      appId: "app_6qqhxqfg6g",
      dataCode: "testrizhi_yiwda3uo",
      record: { uid: 'e2070d81f2e24e24a01858320c088c8c', ... }
    },
    value: { uid: 'e2070d81f2e24e24a01858320c088c8c', ... }
  }
  */
  //阻止所有的 删除类型按钮 点击
  if (payload.options.action === 'delete') {
    return false //阻止原始点击事件
  }


  //自定义按钮
  /**
  {
    instance: { ... },
    options:{
      actionCode: "cust1",
      action: 'custom',
    },
    value: { uid, ... }
  }
  */
  if (payload.options.action === 'cust1') {
    const result = await utils.confirm('提示', '你确认自定义操作吗？')
    if (result === true) {
    	console.log('自定义按钮点击', payload.value)
    }
    return false
  }
}
```

<a id="WraqH"></a>


### payload参数：instance

当前组件的instance实例

<a id="rgpCL"></a>


### payload参数：value

当前行数据

<a id="KeoXp"></a>


### payload参数：options

- actionCode: 操作按钮编码
- action: 操作按钮类型：'create' | 'edit' | 'view' | 'delete' | 'custom'
- appId: 应用id.
- formId: 表单key
- sappId: 菜单id
- uId: 当前记录唯一编号
- processInstanceId：流程实例id。仅配置了《优先访问流程表单》才会返回
- record：当前行数据

<a id="u8mkh"></a>


## list-render-operation 操作列渲染时（3.4.0版本新增）


```typescript
// 操作列渲染时执行时机在列表对操作列进行渲染时
export function onRowOperationRender(payload) {
  const { instance, options: { operationButtons }, value: { data } }= payload
  /*
    operationButtons 操作行所有按钮
    data:{
      uid:"行唯一标识",
      update_time:1669620066000,
      varchar:"我是短文本"
    } 当前行数据
  */
  const buttons = JSON.parse(operationButtons) //需要parse一下 传过来的类型是json格式
  //隐藏每一行当中匹配后的按钮
  if (data.varchar && data.varchar === '我是短文本') {
    //item.props.code code 为设置的编码
    buttons.forEach(item => {
      if (item.props.code === 'delete') {
        item.props.isHide = true
      }
    })
  }
  return buttons
}
```

<a id="IOkKk"></a>


## list-rowclick 行点击时


```typescript
// 行点击事件执行时机在列表原有行操作事件之后
export function onRowClick (payload) {
  console.info('行点击事件', payload)
  ctx.emit('custom:showSubList')
}


/*
行点击事件
{
  instance: {},
  value: {
    "uid": "c24adf0301a34228b8c077394e6a8587",
    "driver_id": "王磊",
    "countNum": 1,
    "sum_net": 1200,
    "sum_rent_amt": 8,
    "dest_warehouse_id": "",
    "billNums": "MJGPFH20240101001181",
    ...
  }
}
*/
```

<a id="mrKCY"></a>


## list-before-rowdelete 行删除前

<a id="uMbMm"></a>


### 触发时机

- 点击行上操作列的删除按钮
- 点击批量删除按钮

<a id="b8vUb"></a>


### 函数返回值

- return false 可以阻止删除
- 没有return，则没有影响


```typescript
export function onDelete (payload) {
  console.log('onDelete:', payload)
  /* 操作列上的删除按钮
  payload: {
    instance: {id: 'LYWvAIlWfQ', type: 'list-view', controlType: 'layout', props: ListViewControlProperty, fieldType: undefined, …},
		value: {SF4: 'c2372c0396b341f5855bcdd88718b837', SF3: 'e5817f0f58df4f36a76665e42d30b168', SF5: '', app_version: ' ', IM1: Array(0), …},
    options: {type: 'delete'}
  }


  批量删除按钮
  payload: {
    instance: {id: 'LYWvAIlWfQ', type: 'list-view', controlType: 'layout', props: ListViewControlProperty, fieldType: undefined, …},
		value: [{SF4: 'c2372c0396b341f5855bcdd88718b837', SF3: 'e5817f0f58df4f36a76665e42d30b168', SF5: '', app_version: ' ', IM1: Array(0), …}],
    options: {type: 'batchDelete'}
  }
  */
  return false
}
```

<a id="OOCMP"></a>


### payload参数：instance

当前组件的instance实例

<a id="rrpWz"></a>


### payload参数：value

- 操作列删除单行数据：当前行数据
- 批量删除：选中的多行数据

<a id="JjCWs"></a>


### payload参数：options

type：

- delete：操作列上的删除按钮
- batchDelete：批量删除按钮

​

<a id="vJMmp"></a>


## list-rows-checked 行选中时（3.3.0版本新增）

<a id="Sx369"></a>


### 触发时机

列表多行勾选

- 批量提交
- 批量删除
- 批量打印
- 二开

<a id="p01S1"></a>


### 函数返回值

无


```typescript
// 行选中事件执行时机，选中checkbox时
export function onRowChecked (payload) {
/* - instance list-view instance
  - option: { "type": "batchSubmit" | "batchPrint" | "checked" } batchSubmit 批量提交选中时  * batchPrint 批量打印选中时 * checked 二开打开选择框时
  - value:{
       "rowKeys": ['eda70d0778154866a1b2a9b451289d3e'], // 列表选择当前行唯一标识
       "rows": [{SF4: 'c92033f4268744cdbf159e68801add8b', SF3: 'e5817f0f58df4f36a76665e42d30b168', SF5: '', app_version: ' ', IM1: Array(0), …}]
       		//列表选择当前行的数据 { dataCode:value }
   }}
*/

  console.info('行选中事件')
}
```

<a id="IqAPK"></a>


### payload参数：instance

当前组件的instance实例

<a id="BNUUe"></a>


### payload参数：value

- rowKeys：string[] ；列表选择当前行唯一标识
- rows：any[]；列表选择当前行的数据

<a id="msrXv"></a>


### payload参数：options

type：

- batchSubmit 批量提交选中时
- batchPrint 批量打印选中时
- batchDelete 批量删除选中时
- checked 二开打开选择框时

<a id="wqw0o"></a>


# 代码事件

<a id="egne3"></a>


## table-change 分页事件

这是全局事件监听，需要写在页面JS的最外层


```typescript
const ctx = exports.ctx;
const utils = exports.utils;
const http = utils.getHttp()
const isMobile = utils.getDevice() === 'mobile'

ctx.on('table-change', (payload) => {
  console.log(payload)
	if (payload.instance.id === '当前列表的id') {
    //区分在列表页中唤起的其他列表触发的change事件
  }
  // {
  //   instance: props.instance as any,
  //   value: {
  //     // 数据总数
  //   	total?: number
  //   	// 当前页
  //   	current?: number
  //   	// 每页条数
  //   	pageSize?: number
  //   	// 指定每页可以显示多少条
  //   	pageSizeOptions?: string[]
  //   }
  // }
})
```

<a id="W7mOL"></a>


# 主动调用

<a id="NpohP"></a>


## custom:showSubList 打开列表明细表抽屉事件


```javascript
// 直接发布事件
ctx.emit('custom:showSubList')
// 或者组装行数据对象
ctx.emit('custom:showSubList', {
  id: 67,
  customer: "test",
  process_instance_id: "a9e0ad78-6d18-4663-876e-42d46bbcb993",
  process_key: "test_test67",
  process_status: "审批中",
})
```

<a id="RGeDt"></a>


## listview:reload-list 刷新列表页数据


```typescript
//不传参数，会根据当前条件刷新
ctx.emit('listview:reload-list', {})


//可选参数示例
ctx.emit('listview:reload-list', {
  value: {
    paginationInfo: {
      current:0,
      pageSize: 5,
    },
    ordersInfo: [{
      column_name: 'uid'
      desc: true
    }],
    queryInfo: [{
      key: "f2",
      key_type: "varchar",
      type: "LIKE",
      value: ["asdfasf"]
    }]
  },
  options: {
    clearSelectedRows: true // 默认清空
  }
})
```

<a id="PsGB9"></a>


### 参数：

- value

- paginationInfo：分页条件
- ordersInfo：排序条件
- queryInfo：查询条件

- options：

- clearSelectedRows。是否清除当前列表选中的行

## 下级条目

- [SimpleSearch 搜索栏](001-SimpleSearch 搜索栏.md)
- [GridTable 表格组件](002-GridTable 表格组件.md)
- [ListPageBtnCreateForm 创建按钮](003-ListPageBtnCreateForm 创建按钮.md)
