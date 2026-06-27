---
title: "SubTable 明细表"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/napf90shdr3yv9ar"
visible: true
slug: "napf90shdr3yv9ar"
doc_id: 187622046
updated_at: "2024-10-10T01:56:47.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "SubTable 明细表"
---
<a id="jcEFL"></a>


## 功能

<a id="uqNIs"></a>


## 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| [caption](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.caption.md) | string | 标题 | ​ |
| [captionTip](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.captiontip.md) | string | 气泡提示语 | '' |
| [datasourceBind](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.datasourcebind.md) | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 绑定数据源 | ​ |
| [dataStorageDoc](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.datastoragedoc.md) | DataStorageDoc | 数据收起简述 | ​ |
| [defaultRows](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.defaultrows.md) | number | 默认填写行数 | 1 |
| [defaultState](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.defaultstate.md) | 'default' | 'readonly' | 默认状态 default=普通 readonly=只读 | 'default' |
| [fixedColumn](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.fixedcolumn.md) | string[] | 固定列 字段 | [] |
| [formKey](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.formkey.md) | string | openType=modal表单模式，formKey为绑定的表单 | '' |
| [isHideCaption](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.ishidecaption.md) | boolean | 隐藏标题 | false |
| [isShowCaptionTip](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.isshowcaptiontip.md) | boolean | 开启气泡提示 | false |
| [labelPosition](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.labelposition.md) | 'top' | 'left' | 标题布局 | 'top' |
| [limitRows](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.limitrows.md) | number | 最小填写行数，并且是默认行数 | 1 |
| [maxHeight](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.maxheight.md) | number | 用户自定义最大高度，默认480 | 480 |
| [mobileShowType](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.mobileshowtype.md) | 'tile' | 'list' | 移动端展现形式 tile=平铺|list=列表 | 'tile' |
| [openType](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.opentype.md) | 'default' | 'modal' | 打开方式（查看，编辑，创建） default列表模式|modal表单模式 | 'default' |
| [printMode](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.printmode.md) | 'col' | 'row' | 打印配置 col=纵向打印|row=横向打印 | 'row' |
| [useCustomHeight](https://file+.vscode-resource.vscode-cdn.net/Users/qiyu/GitLab/model-driven/markdown/model-driven.subtable.usecustomheight.md) | boolean | 使用自定义高度 | false |

<a id="W8iOA"></a>


## 事件

<a id="ew4go"></a>


### list-search 列表数据查询构建时

<a id="BQrgu"></a>


#### 适用场景

1. 明细表数据需要根据条件过滤，如：只希望看到本人的数据、只看某些状态的数据

<a id="dwu7Q"></a>


#### 触发时机

明细表发接口请求前

<a id="kgGjO"></a>


#### 函数返回值

- return [{key: '字段code',type: '',value: [] }]，使用该查询条件
- 不return则会使用默认查询条件


```typescript
// 明细表数据查询构建时
export function onBeforeQuery (payload) {
  // payload.value 为当前的查询条件  SubTableQueryConditions  ↑
  console.log('查询构建', payload)
  /*
  payload: {
    instance: {}
    value: [{
      key: '',
    	type: '',  //'EQ' | 'GT' | 'LT' | 'IN' | 'LIKE' | 'RANGE' | 'GE' | 'LE' | 'CONTAINS_ONE' | 'CONCAT_LIKE' | 'CONTAINS_IN_WITH_SUB_DEPT' | 'NOT_EQ' | 'CONCAT_NOT_EQ'
   		value: []
    }]
  }
  */
  const newQuery = payload.value
  newQuery.push({
    key: '',
    type: '',
   	value: []
  })
  // 必须要return，不return则会使用默认查询条件
  return newQuery
}
```

<a id="awnIJ"></a>


### list-mounted 列表数据返回时


```typescript
// 明细表数据返回时
export function onQueryResponse (payload) {
  // payload.value 为当前明细表的返回值
  console.log('返回结果', payload)
  const newResponse = payload.value
  // 必须要return，不return则会使用默认数据进行渲染
  return newResponse
}
```

<a id="ZI5P3"></a>


### list-change 列表数据变化时


```typescript
// 明细表值发生变化时
export function onSubtableChange (payload) {
  // payload.value是当前发生变化的行数据
  // payload.options.changed 是当前发生变化的行控件的instance
  console.log('明细子表发生变化', payload)
}
```

<a id="JEBAr"></a>


### list-before-insert 列表数据插入前 (3.5.0新增)

<a id="wJ0Wb"></a>


#### 触发时机

点击明细表工具栏上的按钮：

- 增行
- 插行

<a id="HYuML"></a>


#### 函数返回值

- return false：阻止添加行
- return 对象：添加对行按照返回的值添加到明细表行中。⚠️添加以表单形式打开不会生效
- 其他（没有 return）：按照默认方式添加行


```typescript
// 明细表添加前事件 (3.5.0新增)
export function onSubtableBeforeInsert (payload) {
  console.log('onInsert:', payload)
  /*
  payload: {
    instance: {id: 'oOFGN2IZr1', type: 'subtable', controlType: 'list', props: SubTableControlProperty, fieldType: undefined, …},
    options: {type: 'add'},
		value: {jwDTu89pes: '', KRkGSPDPEz: '', EjVvIaQHHi: '', ghVTHgje4l: '', wFuskR1fQ3: []}
  }
  */
  if (payload.options.type === 'add') {
    return {
      EjVvIaQHHi: 123,
      KRkGSPDPEz: "dddd",
      ghVTHgje4l: 321,
      jwDTu89pes: "ddd",
      wFuskR1fQ3: ['ew1', 'vd1']
    }
  } else if (payload.options.type === 'insert') {
    return {
      EjVvIaQHHi: 777,
      KRkGSPDPEz: "aaa",
      ghVTHgje4l: 999,
      jwDTu89pes: "ccc",
      wFuskR1fQ3: ['ew1', 'vd1']
    }
  }
  return false
}
```

<a id="oK3qm"></a>


#### payload参数：instance

当前组件的instance实例

<a id="Gqlng"></a>


#### payload参数：value

空行数据

<a id="W6mjf"></a>


#### payload参数：options

type：add = 增行 / insert = 插行

​

<a id="cQld1"></a>


### list-delete 列表数据删除时

<a id="gF387"></a>


#### 触发时机

点击二次确认弹窗中的确定按钮

<a id="Rht66"></a>


#### 函数返回值

- return false：阻止删除
- 其他：删除当前行数据（没有 return、 return true）


```typescript
// 明细表删除事件
export function onSubtableDelete (payload) {
  /*
  payload: {
    instance: {id: 'oOFGN2IZr1', type: 'subtable', controlType: 'list', props: SubTableControlProperty, fieldType: undefined, …},
    value: [{jwDTu89pes: '', KRkGSPDPEz: '', EjVvIaQHHi: '', ghVTHgje4l: '', wFuskR1fQ3: Array(0), …}],
    options: {
      isNewRow,
      getServicesRows
    }
  }
  */

  // 如果希望阻止删除，则return false
  return false
}
```

<a id="uPb6W"></a>


#### payload参数：instance

当前组件的instance实例

<a id="QtjYI"></a>


#### payload参数：value

当前行数据

<a id="k4lIp"></a>


#### payload参数：options

- 函数：isNewRow(uid: string): boolean

- 辅助工具，传入row.uid。判断当前行是否是本次表单新增的

- getServicesRows(): Record<string, unknown>[]

- 获取新增的行

<a id="nlSVJ"></a>


### list-before-import 列表数据导入前


```typescript

```
