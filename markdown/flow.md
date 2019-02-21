# 基础知识点

- [返回](README.md)

***

- 流程图
  - start 流程开始
  - end 流程结束
  - operation 操作
  - inputoutput 输入输出
  - condition 条件判断
  - subroutine 子程序
  
***

- 效果

```flow
s=>start: 开始流程
e=>end: 流程结束
op1=>operation: 密码检查
cond1=>condition: 是否正确
pwd=>inputoutput: 输入密码
sub=>subroutine: 环境初始化

s->sub->pwd->op1->cond1
cond1(yes)->e
cond1(no)->pwd
```

***

- [返回](README.md)
