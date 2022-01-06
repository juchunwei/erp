```flowchart
st=>start: 开始
e=>end: 结束
setting=>parallel: 基础设置
op1=>operation: 日历
op2=>operation: 员工
op3=>operation: 资源和资源组
op4=>operation: 工序
op5=>operation: 工艺路线
st->setting->op5->e
setting(path1,left)->op1->op5
setting(path2, bottom)->op2->op3->op4->op5
```
