# 流程图

- [返回](README.md)

***

- 流程图元素
  - start 流程开始
  - end 流程结束
  - operation 操作
  - inputoutput 输入输出
  - condition 条件判断
  - subroutine 子程序
  
***

- 流程图

```flow
s=>start: 开始流程
e=>end: 流程结束
op=>operation: 密码检查
cond=>condition: 是否正确
pwd=>inputoutput: 输入密码
sub=>subroutine: 环境初始化

s->sub->pwd->op->cond
cond(yes)->e
cond(no)->pwd
```

***

- [返回](README.md)
