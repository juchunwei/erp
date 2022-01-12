## 安全库存

物料管理->安全库存, 设置物料的最小库存, 运行主计划的时候, 会考虑安全库存, 生成相应的建议

## 安全库存日记账

- 路径: 计划和生产-> 安全库存日记账
- 新建一个日记账, 点击`+` 按钮, 选择要计算的出库记录的`开始日期`,`结束日期`, 仓库, 物料等信息根据需要选择. 系统会自动根据选择期间的出库交易(排除销售退货的交易), 计算出标准方差
- 生成行之后, 点击`计算`按钮, 选择`服务等级`, 进行计算.
- 服务等级: 表示客户下100次订单, 有多少次库存可以满足需求

<div style="margin:0 auto">
<table><thead><tr><th>服务等级</th><th>系数</th></tr></thead>
<tbody>
<tr><td>50%</td><td align="right">0</td></tr>
<tr><td>80%</td><td align="right">0.84</td></tr>
<tr><td>90%</td><td align="right">1.28</td></tr>
<tr><td>95%</td><td align="right">1.65</td></tr>
<tr><td>98%</td><td align="right">2.05</td></tr>
<tr><td>99.86%</td><td align="right">3.0</td></tr>
<tr><td>99.99%</td><td align="right">4.0</td></tr>
</tbody>
</table>
</div>


- 过账之后, 会自动在物料管理->安全库存中生成记录

