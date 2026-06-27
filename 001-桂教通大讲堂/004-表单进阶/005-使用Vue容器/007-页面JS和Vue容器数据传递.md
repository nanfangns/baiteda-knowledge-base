---
title: "页面JS和Vue容器数据传递"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/dpez16ngpuru7t83"
visible: true
slug: "dpez16ngpuru7t83"
doc_id: 187621906
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "百特搭大讲堂"
  - "表单进阶"
  - "使用Vue容器"
  - "页面JS和Vue容器数据传递"
---
页面JS


```javascript
//调用vue容器内部方法
ctx.emit("change1",{type:"",data:{}})
//注：emit的第一个参数 change1可以用户自定义值，只要保证和Vue容器里ctx.on的第一个参数一直即可
     emit的第二个参数 用户可以随意定义
```


Vue容器


```javascript
mounted: function () {
    //在mounted订阅 change1
    ctx.on("change1", (data) => {
      //在这里可以调用Vue容器内function
      console.log(data, "ddd")
    })
  },
```
