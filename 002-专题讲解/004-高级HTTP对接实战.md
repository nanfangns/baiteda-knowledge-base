---
title: "高级HTTP对接实战"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/dzeuxnx8l9nri0gc"
visible: true
slug: "dzeuxnx8l9nri0gc"
doc_id: 187631669
updated_at: "2026-02-27T02:00:42.000Z"
breadcrumb:
  - "专题讲解"
  - "高级HTTP对接实战"
---
<a id="r8UKG"></a>


# 场景说明

业务方自己有开发能力，且功能复杂，平台配置无法实现，经评估后通过调用高级http服务方式可实现对应的业务需求

使用场景：三方系统集成使用平台表单列表能力、复杂场景实现

<a id="xMvKG"></a>


# 使用方法如下

<a id="nX8TU"></a>


## 增删改查接口

参考示例：

[附件: baiteda-client-sdk-demo.zip](../_assets/dzeuxnx8l9nri0gc/baiteda-client-sdk-demo-6995eaf9da.zip)


<a id="Ao9ez"></a>


## 平台配置

<a id="DtoD8"></a>


### 查多（selectMore）

![image.png](../_assets/dzeuxnx8l9nri0gc/image-4d2c946790.png)


<a id="W7phl"></a>


#### 服务配置


![image.png](../_assets/dzeuxnx8l9nri0gc/image-b5db20854e.png)


![image.png](../_assets/dzeuxnx8l9nri0gc/image-9917d4878d.png)


<a id="f38ts"></a>


#### 使用场景

列表数据加载时调用该服务可实现对数据的查多操作

<a id="frCBg"></a>


#### 案例

列表数据加载时调用该服务将查询的数据展示


![image.png](../_assets/dzeuxnx8l9nri0gc/image-dee72a6f6f.png)


<a id="ZFyE1"></a>


#### 参考示例

示例项目：baiteda-client-sdk-demo

> superhttp模块下SuperHttpServiceController接口中的selectMore

<a id="KN2TA"></a>


### 新增（insert）

<a id="Ft0u2"></a>


#### 服务配置


![image.png](../_assets/dzeuxnx8l9nri0gc/image-dcd97bb278.png)


<a id="jc9HC"></a>


#### 使用场景

创建数据时调用新增服务可实现对数据的新增

<a id="c31mX"></a>


#### 案例

在列表上点击创建单据，打开表单录入数据点击保存，实现调用新增服务


![image.png](../_assets/dzeuxnx8l9nri0gc/image-e40ef2c08f.png)


![image.png](../_assets/dzeuxnx8l9nri0gc/image-dac39076b6.png)


<a id="TuzvK"></a>


#### 参考示例

示例项目：baiteda-client-sdk-demo

> superhttp模块下SuperHttpServiceController接口中的insert

<a id="cqBwz"></a>


### 修改（update）

<a id="NEWvl"></a>


#### 服务配置


![image.png](../_assets/dzeuxnx8l9nri0gc/image-d44c6625c8.png)


<a id="MjBvq"></a>


#### 使用场景

对数据进行修改调用该服务可实现修改操作

<a id="rtsxL"></a>


#### 案例

点击列表修改，在弹出表单修改完成数据，点击保存调用修改服务


![image.png](../_assets/dzeuxnx8l9nri0gc/image-0e6994a3e0.png)


<a id="pMNRo"></a>


#### 参考示例

示例项目：baiteda-client-sdk-demo

> superhttp模块下SuperHttpServiceController接口中的update

​

<a id="cMN2m"></a>


### 删除（delete）

<a id="cvAge"></a>


#### 服务配置


![image.png](../_assets/dzeuxnx8l9nri0gc/image-31fd5bc7bf.png)


<a id="cjWSS"></a>


#### 使用场景

对数据进行删除时调用该服务可实现删除

<a id="DOhLp"></a>


#### 案例

点击列表删除，调用删除服务


![image.png](../_assets/dzeuxnx8l9nri0gc/image-b073b096ab.png)


<a id="Tm4kT"></a>


#### 参考示例

示例项目：baiteda-client-sdk-demo

> superhttp模块下SuperHttpServiceController接口中的delete

<a id="FAkAW"></a>


### 查单（selectOne）

<a id="vZkVO"></a>


#### 服务配置


![image.png](../_assets/dzeuxnx8l9nri0gc/image-76c4f5c4c4.png)


<a id="HvNKo"></a>


#### 使用场景

表单数据加载时调用该服务可实现对数据的查询操作

<a id="n9QRU"></a>


#### 案例

列表查看数据时调用查单服务，实现对表单数据的查看


![image.png](../_assets/dzeuxnx8l9nri0gc/image-63c15eb02f.png)


<a id="GZA1h"></a>


#### 参考示例

示例项目：baiteda-client-sdk-demo

> superhttp模块下SuperHttpServiceController接口中的selectOne

鉴权方式参考

[鉴权管理](https://baiteda.yuque.com/czwxoe/avp3qe/hgng8f32eszzx82g)
