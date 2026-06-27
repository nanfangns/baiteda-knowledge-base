---
title: "GridTable 表格组件"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/ihrgfaq9e6rqalno"
visible: true
slug: "ihrgfaq9e6rqalno"
doc_id: 187622045
updated_at: "2024-10-10T01:36:05.000Z"
breadcrumb:
  - "前端开发"
  - "前端组件属性及事件"
  - "ListView 列表页"
  - "GridTable 表格组件"
---
<a id="EYcLw"></a>


## 功能

<a id="zaBoV"></a>


## 属性

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| headers | Column[] | 列 | [] |
| isFixedHeader | boolean | 冻结表头 | false |
| isShowCustomColumns | boolean | 显示自定义表头 | true |
| isShowSelection | boolean | 显示选择框 | false |
| isShowToolbar | boolean | 显示工具栏 | true |
| selectionType | undefined | 'multiple' | 'single' | 选择类型 |  |

<a id="MjWKw"></a>


## 子组件


[公共属性定义](https://baiteda.yuque.com/staff-shgita/nbg92z/zzw6la0o4nqdgu5e#OQS4G)

<a id="ZNcZt"></a>


### ArrayColumn 数组类型列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| datasourceBind | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 关联数据源 | ​ |
| optionConfig | 'none' | 'custom' | 'datasource' | 选项配置 | 'none' |
| options | [OptionSetting](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#xt6xr)[] | 自定义选项 | [] |

<a id="ElzQG"></a>


### AutoNumber 自动编号列

无特殊属性，参考公共属性

<a id="rE9Qj"></a>


### CustomColumn 自定义列

无特殊属性，参考公共属性

<a id="TEZGP"></a>


### DecimalColumn 数字列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| datasourceBind | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 关联数据源 | ​ |
| micrometer | false | 千分位展示 | false |
| optionConfig | 'none' | 'custom' | 'datasource' | 选项配置 | 'none' |
| options | OptionSetting[] | 自定义选项 | [] |
| percentageFormat | boolean | 百分比格式化 | false |
| precision | number | '' | 保留几位小数 | 0 |

<a id="qrKxD"></a>


### DepartmentColumn 部门列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| displayLevel | number | 部门显示层级 | 1 |

<a id="BsKIL"></a>


### EmployeeColumn 人员列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| datasourceBind | SuperDataSourceBind | 关联数据源 | ​ |

<a id="iFwVA"></a>


### FileColumn 文件列

无特殊属性，参考公共属性

<a id="yUJmb"></a>


### ImageColumn 图片列

无特殊属性，参考公共属性

<a id="cWErG"></a>


### LocationColumn 地址列

无特殊属性，参考公共属性

<a id="I1TtW"></a>


### OperationColumn 操作列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| limit | number | 最多展示操作数 | 3 |
| showType? | 'text' | 'icon' | 'iconText' | *(Optional)* 显示效果 | 'icon' |
| children | [OperationItem](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#OB5k4)[] | 操作按钮 | [] |

<a id="sremG"></a>


### OrderColumn 序号列

无特殊属性，参考公共属性

<a id="bfyit"></a>


### TextColumn 长文本列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| escapeHTML | boolean | 保留富文本格式 | true |
| lineEllipsis | number | 行数设置 | 1 |

<a id="M5lg5"></a>


### TimescopeColumn 日期区间列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| dateType | DateType | 日期展示格式 | 'date' |

<a id="FF4LX"></a>


### TimestampColumn 日期列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| dateType | DateType | 日期展示格式 | 'date' |

<a id="wdPBn"></a>


### VarcharColumn 短文本列

|  |  |  |  |
| --- | --- | --- | --- |
| 属性 | 类型 | 名称 | 默认值 |
| datasourceBind | [DataSourceBind](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#h1NkF) | 关联数据源 |  |
| lineEllipsis | number | 最大行数 |  |
| optionConfig | 'none' | 'custom' | 'datasource' | 选项配置 | 'none' |
| options | [OptionSetting](https://baiteda.yuque.com/staff-shgita/nbg92z/evpg3ttw4qcqskhk#xt6xr)[] | 自定义选项 | [] |
