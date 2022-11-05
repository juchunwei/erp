﻿## 基础设置

### 供应商
- 路径: 采购->供应商
- 根据需要设置供应商的信息, 合同信息, 语言等. 打印订单时根据供应商的语言, 自动调出相应语言的报表
- 供应商编号:
    - 手工设置或为空.
    - 在`自动编号`中设置. 
    - 在`供应商组`中设置, 该设置优先级对于`自动编号`中的设置. 

- 供应商中设置的信息会自动带到采购单中, 比如地址, 税率,是否含税, 报表模板等. 其中`税率`, 如果`物料`上设置了`税率`, 则覆盖`供应商`上设置的税率.
- 可以针对供应商设置采购单的`订单编号`, 如果没有设置, 则使用`自动编号`中的`采购订单`编号规则. 如果要设置供应商的订单编号, 在`自动编号`中**新增**一个类型为`采购订单`的编号规则,, 然后选择**新增**的编号规则, <font color="red">不要选择系统默认的编号</font>.

### 采购价格
可以根据`供应商组`设置不同的价格体系和折扣
- 路径: 物料管理->采购价

### 订单和合同打印
在管理->`报表设计`中设计报表的样式

## 操作
- 路径: 采购->采购订单
- 采购订单保存后, 如果设置了`预付款`, 会根据参数设置(管理->设置->参数页), 自动生成`付款申请`或者`付款日记账`, 带出**此时**供应商中设置的银行账户等信息, 付款后, 财务部门过账.
    - 付款申请: 点击`付款`按钮, 会打开`付款日记账`页面, 核对信息后, 保存并过账, 生成`应付账款交易记录`.
- 收货: 参见[收货单](../Onhands/Receipt.md)
- 发票: 参见[供应商发票](../Financial/AP/Invoice.md)
- 付款: 参见[付款日记账](../Financial/AP/PaymentJournal.md)