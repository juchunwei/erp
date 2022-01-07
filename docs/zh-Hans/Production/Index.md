## 基础设置
---
```flowchart
st=>start: 开始
e=>end: 结束
setting=>parallel: 基础设置|past
op1=>operation: 日历
op2=>operation: 员工
op3=>operation: 资源和资源组
op4=>operation: 工序
op5=>operation: 工艺路线

st->setting->op5->e
setting(path1,left)->op1->op3
setting(path2, bottom)->op2->op3->op4->op5
```

### 生产流程
---

```flowchart
st=>start: 开始
e=>end: 结束生产订单
order=>parallel: 销售订单
op1=>operation: 手工创建生产订单
sch=>subroutine: 主计划
prod=>parallel: 生产订单
op2=>operation: 作业日记账
op3=>operation: 生产领料
op4=>operation: 生产入库

st->order->prod->e
order(path1, bottom)->sch->prod
order(path2, right)->op1->prod
prod(path1, bottom) ->op2->e
prod(path2, left)->op3->e
prod(path3, right)->op4->e
```

### 计件工资流程
---
```flowchart
st=>start: 开始
s=>end: 结束
para=>parallel: 基础设置|past
op1=>operation: 工序
op2=>operation: 物料
op3=>operation: 计件单价
prod=>operation: 生产订单
op4=>operation: 作业日记账
op5=>operation: 计算工资


st->para
para(path1, bottom)->op1->op3
para(path2, right)->op2->op3
op3->prod->op4->op5->e
```

