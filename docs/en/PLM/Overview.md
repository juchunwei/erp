## Flowchart

```flowchart
st=>start: Start
e=>end: End
setting=>parallel: Settings|past
op1=>operation: Number sequence
op2=>operation: Document type
op3=>operation: Folders
op4=>operation: Folder permissions
op5=>operation: Workflow
op6=>operation: Create document
op7=>operation: Create change order
op8=>operation: Workflow
op9=>operation: Update the status and version of the document

st->setting->op5->e
setting(path1,left)->op5->op2
setting(path2, bottom)->op1->op2->op3->op4->op6->op7->op8->op9->e
```

## Basic settings

1. Number sequence：Generate the No. for document or change order。Administration-->Basic settings-->Num seqs，the `Num seq type` field should be PLM.
2. [Document Type](DocumentType.md)   
3. [Folder](Folder.md) and  Folder permissions.
5. [Change order type](ChangeOrderType.md)
6. Workflow
7. Organizations and employees
8. [Change order](ChangeOrder.md)

## Operations

1. 新建文档。文档的生命周期为原型。
2. 创建变更单，记录变更原因，选择要变更的文档，上传附件，提交审核。审核通过后，对应的文档的生命周期会改为变更单中的设置
3. 文档中可以查看附件和变更记录
