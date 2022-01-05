### 一、报表控件说明:

1. logo: XRPictureBox名称为logo
2. 公司名称: 文本控件名称为companyName
3. 公司地址: companyAddress
4. 电话: companyTel
5. 自定义的html内容: contractContent
6. 物料属性列头: 以InventDimTitle开头, 如果没有启用对应的物料属性, 报表运行时会自动隐藏该列

### 二、报表参数

sql查询参数:tenantId, 运行时自动设置为租户的id, 如果不设置表示读取所有子公司的数据

