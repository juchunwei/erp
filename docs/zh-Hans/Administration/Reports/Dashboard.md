## ͼ��
- �������Ǳ������ʾ
- **����**,
- **����**, 
- **�ļ�**: javascript���ļ���, ����js��չ��, ���ϴ���������, ����:
  ```js
  (function () {
    app.customWidgets.CurrentJobWidget = function () { //CurrentJobWidgetΪclass����, ��Ҫ�����޸�
    //�ű�����
      var _widget;       
        var _widgetBody;

        this.init = function (widgetManager) {
            _widget = widgetManager.getWidget();
            _widgetBody = _widget.find('.card-body');
        };
        //����ĺ���, ���ڶ�ȡ����֮��, ����ҳ�����ʾ   
        this.showData = function (data) {
            _widgetBody.empty();
            /*ҳ����ʾ����, ������Ҫ�޸�*/
            data.forEach(d => {
                var endDate = moment(d.EndDate);

                var group = $(`<div class="mb-10"></div>`);
                var row = $(`<div class="d-flex justify-content-between"></div>`);               
                row.append(`<div class="form-group"><label>������:</label><label>${d.ProdId}</label></div>`);
                row.append(`<div class="form-group"><label>��Ա:</label><label>${d.Name}</label></div>`);
                group.append(row);
                row = $(`<div class="d-flex justify-content-between"></div>`);  
                row.append(`<div class="form-group"><label>��Ʒ����:</label><label>${d.ItemCode}</label></div>`);
                row.append(`<div class="form-group"><label>��Ʒ����:</label><label>${d.ItemName}</label></div>`);
                group.append(row);
                row = $(`<div class="d-flex justify-content-between"></div>`);
                row.append(`<div class="form-group"><label>ʵ�ʿ�ʼ����:</label><label>${moment(d.ActualStartDate).format('YYYY-MM-DD')}</label></div>`);
                row.append(`<div class="form-group ${endDate < moment() ? "red" : ""}"><label>�ƻ���������:</label><label>${endDate.format('YYYY-MM-DD')}</label></div>`);
                group.append(row);
                var progress = "25%";
                var finishedQty = d.JournalQty + d.FinishedQty;

                if (finishedQty)
                    progress = finishedQty / (d.Qty || 1) * 100;
                else
                    progress = d.ActualHours / (d.WorkHours || 1) * 100;
                progress = app.formatNum(progress, 2) + '%';

                group.append(`<div class="progress h-30px"><div class="progress-bar bg-success" role="progressbar" aria-valuenow="0" style="width:${progress};" aria-valuemin="0" aria-valuemax="100">${progress}</div></div>`);
                _widgetBody.append(group);
            });

        }       
     }
  })();
  ```
- **����**: html, ����ͼ����ʾ������

```html
<div class="card card-custom h-100">
    <div class="card-header">
        <div class="card-title">
            <h4>��ǰ����</h4>
        </div>
    </div>
    <div class="card-body">
    </div>
</div>
```
- **����**: sql���, �����ݿ��ȡҪ��ʾ������
## �Ǳ��
- �����ͼ��֮��, ��ͼ����ӵ��Ǳ��
- **����**: �Ǳ�������, ������ʾ��**����̨**, *�Զ��屨��*��
- **���**: �Զ��屨������
- **���**: Ȩ��
- **����**: һ�㲻��Ҫ�ֹ�����, ��***Ԥ��***��ť֮��, ��������ͼ��, ����ͼ��Ĵ�С��λ�õ�

## �Ǳ������

![Dashboard](dashboard.png)

- ������Ͻǵ�����(����)��ť
- �༭ģʽ: ��֮��, ��������Զ���ͼ��, ������ͼ���λ�úʹ�С
- ˢ��: �Զ�ˢ�����ݵļ��
- ����: ����֮��, ֻ��Ե�ǰ�ĵ���������, ��ͬ�ĵ��Կ������ò�ͬ�ı���
- ɸѡ: ����ɸѡ����, **����**��Ҫ��ͼ���е�sql���**��ѯ����**��Ӧ, ֵֻ��Ե�ǰ������Ч


![Dashboard Setting](dashboard-setting.png)