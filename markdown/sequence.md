# 时序图

- [返回](README.md)

***

- 时序图元素
  - `participant 时序对象`
  - `title 标题`
  - `- 实线`
  - `-- 虚线`
  - `> 箭头`
  - `时序对象1-->时序对象2:说明信息`
  - `Note left/right of 时序对象:文本 在时序对象左边或或者右边显示文本`

***

- 时序图

```sequence
title:简单bs架构时序图

participant 浏览器
participant 服务器
participant 数据库

浏览器->服务器: request
Note right of 浏览器: 表单数据
服务器-->浏览器: 请求数据校验错误
Note left of 服务器: 校验错误信息应答
服务器->数据库: 数据访问层
Note right of 服务器: 查询参数
数据库-->服务器: 数据返回
Note left of 数据库: 查询结果
服务器-->浏览器: response
Note left of 服务器: 业务数据信息应答

```

***

- [返回](README.md)
