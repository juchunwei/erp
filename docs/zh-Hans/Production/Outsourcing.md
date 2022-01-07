## 

## 流程

```flowchart
st=>start: 开始
e=>end: 结束
op1=>operation: 物料(设置计划类型和供应商) 
op2=>operation: 物料清单(设置物料的外协供应商)
cond=>condition: 提供原材料给外协供应商?
op3=>operation: 生产订单
op4=>operation: 外协作业
op5=>operation: 采购订单
op6=>operation: 收货单
op7=>operation: 收货质检
sub1=>subroutine: 委托加工单
op11=>operation: 给外协发原材料
op8=>operation: 外协发货
op9=>operation: 自动创建对应外协工序的作业日记账

op10=>operation: 生产领料
st->op1->op2->op3->op4->cond
cond(yes)->sub1->op11->op8->op6
cond(no)->op5->op6
op6->op7->op9->e
```

## 

### 说明

- 物料的计划类型为`外协`(需要提供原材料给外协, 生成`委托加工单`)或`外协采购`

- 在BOM中设置物料在哪个`工序`使用和`外协供应商`

- 创建生产单时, 根据BOM中的设置，和物料的`计划类型`，带出BOM中设置的供应商或者物料基本信息中设置的供应商。

- 计划和生产-->外协管理-->外协作业, 可修改数量,交货期和供应商信息, 点击`确认`, 可以根据物料的计划类型, 自动生成采购单或者委托加工单

- 采购单:
  
  - 生成的采购单的参考类型为生产,  没有参考单号. 
  - 订单行的RefId为`生产BOM`的Id, RefOrderType为`生产领料`
  - 生产BOM的SourceOrderId为采购单的Id
  - 库存预留表中, 自动创建BOM和采购单行的对应关系
  - 收货单
  - 质检结束后, 作业日记账中自动添加对应的`生产作业`
  - 其余按正常的采购流程

