## Change order

1. Create a new Change order.

2. Fields:
   
   | Field             | Description                                                                                                                    |
   | ----------------- | ------------------------------------------------------------------------------------------------------------------------------ |
   | Change order type | The system generate the order number base on the setting of the selected [Change order type](ChangeOrderType.md).              |
   | Folder            | - Please refer [Folder](Folder.md).  - Generate the Document Veriosn.<br/>- Get the default workflow.<br/>- The filter for the `Document` column in the line table.                                                                                            |
   |                   |  |

3. Lines:
   
   - Create lines and then choose the `Document`. The document list base on the selected Folder.
   - Fill out the other colums if need.

4. Attachments:
   
   - Choose a line first, then click the `Attachments` tab.
   - Click the <font color="blue"><b>+</b></font> button on the attachments table header, choose a file upload.

5. Save the order and click `Workflow` button -> Submit. The status of the `Change order` changed to Pending.

6. The user selected in the workflow who need review the change order, will get the notification to approve it.

![Change Order](../images/PLM/change-order.png)

The notification:

1. Click the notification, the system will redirect to the `Change order` page.
2. Click `Workflow` button, to Approve or Reject.
3. Email notification:
   - Go to Administration->Settings->Email(SMTP), setup the email sender information.
   - Edit the user and check `Enable email notification`.

![Changeorder Workflow](../images/PLM/changeorder-workflow.png)