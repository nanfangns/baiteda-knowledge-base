---
title: "表单/列表二开指南"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/gzdzq5dqdaao6ztl"
visible: true
slug: "gzdzq5dqdaao6ztl"
doc_id: 187621952
updated_at: "2026-01-15T10:19:07.000Z"
breadcrumb:
  - "专题讲解"
  - "表单/列表二开指南"
---
<a id="R877z"></a>


## 1.页面URL参数说明

<a id="S6Rg4"></a>


### 1.1表单页面url组成

> **示例1，标准路径:**
>
> https://test.baiteda.com/apps/desktop/sapp/app\_rsjuc9rb7y/sapp\_1xpudm70je/box/list/form\_9wgmab6a9e
>
> ​
>
> **示例2，多级路径:**
>
> https://localerjimulu.yigowork.com/lowcode/tools/apps/desktop/sapp/btdev\_system\_app/btdev\_pu4anmqwlz/box/list/btdev\_form\_pomuoj0dnw?menuId=9044516689140671&type=view&header=none&open\_mode=BLANK\_PAGE
>
> ​
>
> **示例3， 开启启动器的路径（**⚠️**4.0.0 版本pc端新增功能，移动端不存在此路径）**
>
> https://test.baiteda.com/apps/desktop/multipleTabs/sapp/app\_rsjuc9rb7y/sapp\_1xpudm70je/box/list/form\_9wgmab6a9e
>
> ​

**蓝色为域名**：如果有多级路径则都涵盖在这一段。

**固定路径**：PC或移动区分。PC和移动端会根据 逻辑屏幕分辨率 计算宽度，小于600自动跳转至移动端

- /apps/desktop
- /apps/mobile

**路由路径**：见下表

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 页面 | url | router | 开启启动器的url （​4.0.0 版本pc端新增功能） | 开启启动器的router（​4.0.0 版本pc端新增功能） |
| 无菜单页面  表单页面  vue页面  自由页面 | /sapp/app\_690wtn00im/sappId/form\_h6ouSnkjil/7f70847d-adb0-489b-8451-ad3d06222462 | /sapp/:appId/:sappId/:formId/:uId? | /multipleTabs/sapp/app\_690wtn00im/sappId/form\_h6ouSnkjil/7f70847d-adb0-489b-8451-ad3d06222462 | /multipleTabs/sapp/:appId/:sappId/:formId/:uId? |
| 菜单导航 - 列表页面 | /sapp/app\_rsjuc9rb7y/sapp\_1xpudm70je/box/list/form\_9wgmab6a9e | /sapp/:appId/:sappId/box/list/:formId | /multipleTabs/sapp/app\_rsjuc9rb7y/sapp\_1xpudm70je/box/list/form\_9wgmab6a9e | /multipleTabs/sapp/:appId/:sappId/box/list/:formId |
| 有菜单页面  表单页面  vue页面  自由页面 | /sapp/app\_rsjuc9rb7y/sapp\_1xpudm70je/box/form/form\_tlpeokh8bd/08513068116558653 | /sapp/:appId/:sappId/box/form/:formId/:menuId | /multipleTabs/sapp/app\_rsjuc9rb7y/sapp\_1xpudm70je/box/form/form\_tlpeokh8bd/08513068116558653 | /multipleTabs/sapp/:appId/:sappId/box/form/:formId/:menuId |
| 报表页面 | /sapp/app\_rsjuc9rb7y/sapp\_1xpudm70je/box/report?menuId=22601103724973792&src=//testqw.baiteda.com/report/ureport/view?\_u=ego-knqrm25su4 | /sapp/:appId/:sappId/box/report | /multipleTabs/sapp/app\_rsjuc9rb7y/sapp\_1xpudm70je/box/report?menuId=22601103724973792&src=//testqw.baiteda.com/report/ureport/view?\_u=ego-knqrm25su4 | /multipleTabs/sapp/:appId/:sappId/box/report |
| 审批页面  待办、已办、申请 | /approval/app\_pheaonu0mv/7f70847d-adb0-489b-8451-ad3d06222462 | /approval/:appId/:taskId | 无 | 无 |
| 流程列表查看页面 | /process/app\_em6vvett3v/02d55d58-558b-4cea-a554-b07e163082a3?additional\_query={}&header=none | /process/:appId/:processInstanceId | /multipleTabs/sapp/app\_em6vvett3v/sappId/box/process/02d55d58-558b-4cea-a554-b07e163082a3?additional\_query={}&header=none | /multipleTabs/sapp/:appId/:sappId/box/process/:processInstanceId |
| 固定审批页面表单 | /approval/btcs\_app\_7yfsxtgj1g/fixedForm/btcs\_form\_hwp603f2ph?taskId=dd3d8228-ece9-471a-85c2-6d0588993bd3&tenantId=btcs | /approval/:appId/fixedForm/:formKey | 无 | 无 |
| 知会页面 | /notice/app\_pheaonu0mv/31234620-136a-4a8a-a22e-400ede283194 | /notice/:appId/:noticeId | 无 | 无 |
| 外链页面 | /external/fmINVr | /external/:appKey | 无 | 无 |

参数解释：

- :appId：应用ID
- :sappId：菜单ID
- :formId：表单ID
- :menuId：菜单项ID
- :taskId：任务ID
- :noticeId：知会ID
- :appKey：依赖后端生成的id
- :processInstanceId：流程实例 id，在列表页面中有该字段值

<a id="U8CQJ"></a>


### 1.2表单页面url上有以下控制参数

示例：http://test.baiteda.com/mobile/process/yl\_app\_ccfwm0fwdz/yl\_al6biwqd1m/yl\_form\_hy6e8x618q/333939ef09964afda96bc2fd4bb269b0?type=view&header=none&stayhere&open\_mode=BLANK\_PAGE

1. header=none，表单没有顶部logo，一般用于iframe嵌套时使用
2. stayhere，平台现有特性是：PC端打开移动连接会自动跳转为PC页面，反之亦然。stayhere参数的功能则是禁止该功能，主要使用的场景：PC端侧边栏打开的表单希望以移动方式呈现的需求
3. open\_mode=BLANK\_PAGE，不显示左侧菜单
4. noupdateopener=1，阻止当前表单尝试对opener页面刷新。直接关闭当前页面。
5. type=view, view只读页面，create：新增页面， edit： 编辑页面， 主要用在列表页打开的表单上。
6. nominwidth=1，去掉当前页面的最小宽度限制

​

​

<a id="pfPoT"></a>


## 2.二次开发有两种途径

- 表单二开：基于平台页面的生命周期，通过事件的方式进行JS、CSS的业务逻辑开发
- Vue容器：基于平台组件体系进行自定义组件的开发，提供额外能力。如集成 地图、电子签章等组件

可以编写JS、Vue的语法，使用Ant Design Vue、 Vant 组件能力。

<a id="bdl9C"></a>


## 3.组件定义 instance

以下用一个输入框组件作为示例：


```json
{
    "id": "8ju86f673mtp7iq",
    "type": "input",    //组件类型
    "props": {    //所有的组件属性
        "isHide": false,    //是否隐藏
        "caption": "单行文本",    //标题文字
        "isHideCaption": false,    //隐藏标题文字
        "defaultState": "default",
        "labelPosition": "top",    //标题文字对齐方式 top / left
        "placeholder": "请输入",    //提示文字
        "required": false,        //必填校验
        "requiredMessage": "",    //必填错误信息
        "dataBind": {        //数据绑定
            "dataCode": "app_k53xpva70l_bxd",
            "fieldCode": "reason"
        },
        "defaultValue": "🚀🚀🚀",    //默认值
        "maxLength": 50,
        "minLength": 0,
        "regularRules": {
            "stencilName": "",
            "expression": "",
            "errMessage": ""
        }
    },
    "controlType": "form",    //组件类型
    "fieldType": "varchar",    //组件数据类型
    "pageStatus": 2    //页面状态
}
```


defaultState：

- default = 可编辑
- readonly = 只读

改变组件属性，即可使组件状态变化，如将该组件隐藏，只需要将isHide=true，即可实现，在二开时操作组件属性提供了一组API，以帮助开发者完成所需工作，具体见 表单二开 章节

<a id="YlwEU"></a>


## 4.组件数据类型 fieldType

数据类型示例:

- 短文本 varchar 任意字符串。 单行文本、下拉单选、单选、关联单选
- 长文本 text 任意字符串。多行文本、富文本
- 数组 array 数组字符串 ['', '', '' ...]。 下拉多选、多选
- 数值 decimal 9007199254740991 ～ -9007199254740991。金额、数字、评分、计算公式
- 日期 timestamp 1618108059582。日期、日期区间
- 人员 people['QiYu']。人员
- 部门 department['19', '20']。部门
- 附件 file['ded2594020e6d0affa0a5199e8cebf99']。附件
- 图片 image['ded2594020e6d0affa0a5199e8cebf99']。图片
- 自动编号 auto\_number"0001"自动编号

<a id="Kz71z"></a>


## 5.组件类型 controlType

- layout：布局，如：分组、标签页、栅格布局
- form：表单，如：单行文本、下拉单选、数字、日期等
- base：基本组件，如：按钮、分割线、超链接、说明文字
- list：列表，如：列表、明细表
- column：列表列
- search：查询，如：简单查询

<a id="BZd9O"></a>


## 6.页面类型 pageStatus

- 1 = 只读页面
- 2 = 可编辑页面
- 5 = 打印页面

<a id="tnuX6"></a>


## 7.ES6语法支持

JS编码均支持直接书写ES6语法（包括async/await等），为保证浏览器兼容性，平台会编译兼容至ES5

<a id="m2ERc"></a>


## 8.表单的数据结构

表单背后存储的数据结构如下：

核心是记录下表单中所有的 controlId 的值，其结构是 约等于 当前页面的嵌套结构。

​


```typescript
{
    [dataViewId: string]: {
        [controlId: string]: unknown
    },
    [titleControlId: string]: {
        "descript": string,
        "submit_user": Object,
        "submit_dept": Object,
        "current_approvar": string[],
        "submit_time": string,
        "subject": null,
        "printUrl": string,
        "bizKey": string
    },
    "variables": {},
    "delete_ids": {
        [subtableId: string]: string[]
    }
}
```


controlId 代表了页面中每个组件的id，其 值 也与平台中组件数据类型一致，如 单行输入框 是 短文本；数字输入框 是 数字；

这个数据结构也被成为 state，在后续的API中有相关的 getState / setState / setStates


```json
{
    "na78g8xysf3ixiq": {
        "8ju86f673mtp7iq": "zxcvasdf",
        "npp2574891bgcg0": "1619246218265",
        "lzlhz2b8vlivtim": [
            "19"
        ],
        "67d2ex0uenoov7h": [
            "QiYu"
        ],
        "ofy7149tk7qxq9i": "CNY",
        "yb7hwxvqlbcs2jg": {
            "amount": 12333,
            "currency": ""
        },
        "qz7ixzedtv8koa5": "1617863818265",
        "0tj7triaeoo83cc": [],
        "gcih9terpe5k2bn": [],
        "cw315m67cwuno6o": "",
        "alwdwd9ap940989": [],
        "qhmtsd7nw72at8x": [],
        "uid": "d5e539bc5f5a4851901d7e197b61d3bd"
    },
    "o9l6tu0j6equ7zi": {
        "descript": "",
        "submit_user": {
            "employee_name": "戚雨",
            "employee_en_name": "戚雨",
            "employee_id": "QiYu",
            "email": "qiyu@byteluck.com",
            "avatar_url": "https://wework.qpic.cn/bizmail/VEEjIUuN4JFLJJGa1Xx1oueyiaTbicWNtibIeaAbxibib3P0OwINGHHSpuQ/0",
            "department_id": "30",
            "department_name": "前端部",
            "department_en_name": null,
            "leader_eid": "JiangNan",
            "terminated": null,
            "checked": null,
            "tenant_id": "check",
            "external_user": false,
            "avatar_big": "https://wework.qpic.cn/bizmail/VEEjIUuN4JFLJJGa1Xx1oueyiaTbicWNtibIeaAbxibib3P0OwINGHHSpuQ/0",
            "avatar_small": "https://wework.qpic.cn/bizmail/VEEjIUuN4JFLJJGa1Xx1oueyiaTbicWNtibIeaAbxibib3P0OwINGHHSpuQ/0",
            "msg_relation_type": "WX",
            "phone": "17705186024",
            "manage_dept_ids": null,
            "manage_dept_name": null,
            "manage_dept_en_name": null,
            "belong_dept_ids": "19,30",
            "belong_dept_name": null,
            "belong_dept_en_name": null,
            "belong_dept_id_list": [
                "19",
                "30"
            ],
            "employee_card": null,
            "telephone": null,
            "sort": 9999,
            "gender": 1,
            "sequence": "前端架构师"
        },
        "submit_dept": {
            "department_id": "30",
            "department_name": "前端部",
            "department_en_name": null,
            "display_value": null,
            "checked": null
        },
        "current_approvar": [],
        "submit_time": "2021-04-10 14:39:08",
        "subject": null,
        "printUrl": "",
        "bizKey": "0001"
    },
    "variables": {}
}
```

<a id="jujok"></a>


## 9.CSS定制

每个表单组件都会有一个标识符，可以通过data-cid选择器找到它：


```css
[data-cid='8ju86f673mtp7iq'] {
  background: greenyellow;
}
```


⚠️注意：由于组件内部结构升级，可能会影响内部DOM结构，使用样式选择器需要慎重

## 下级条目

- [自定义第三方列表页](001-自定义第三方列表页.md)
- [JS事件与Vue容器联动](002-JS事件与Vue容器联动.md)
- [代码示例-Vue容器](003-代码示例-Vue容器.md)
- [事件](004-事件.md)
- [Vue容器](005-Vue容器.md)
- [vue三方组件开发](006-vue三方组件开发.md)
- [常见问题](007-常见问题.md)
