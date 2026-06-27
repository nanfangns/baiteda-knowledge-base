---
title: "流程脚本二开指南"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/sw1za9n9rt7bgwez"
visible: true
slug: "sw1za9n9rt7bgwez"
doc_id: 187621941
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "平台扩展开发"
  - "流程脚本二开指南"
---
<a id="UH7mD"></a>


### 1.简介

本节主要介绍如何在流程引擎中编写表达式，以及如何使用提供的对外暴露的函数。

​

流程中的表达式使用的是Groovy动态表达式引擎。

Groovy语言中兼容了java语言的核心基础语法，对于开发人员几乎不需要学习成本，即可快速使用。

​

例如：

基础数据类型和集合类型的声明


```java
String str = "123";
int number = 1;

List list = new ArrayList();
list.add("groovy");
```


逻辑分支


```java
if() {

} else {

}

for(...) {}

while () {}
```

<a id="NwiC4"></a>


### 2.瞬时变量

在流程提交时通知指定的参数传入，变量在这一次的执行过程中可用。

如何使用？

假如传入的瞬时变量的参数key为transientParam，且参数值是个整型。

如：


```json
{
	"transientParam":20
}
```


使用变量


```groovy
if (transientParam > 20) {
	……
}
```

## 下级条目

- [内置函数使用场景](001-内置函数使用场景.md)
- [内置函数](002-内置函数.md)
