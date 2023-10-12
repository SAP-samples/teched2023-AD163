# Create Process <a name="process"></a>

<!-- description --> In this exercise, you will create a process to update the billing block based on the Approval

## Table of Contents <a name="tableContents"></a>
- [Create Process ](#create-process-)
  - [Table of Contents ](#table-of-contents-)
  - [Overview ](#overview-)
    - [Add Event Trigger to Process ](#add-event-trigger-to-process-)
    - [Add Condition to match Sales Order ](#add-condition-to-match-sales-order-)
    - [Add Action to read Sales Order Items ](#add-action-to-read-sales-order-items-)
    - [Create Approval Sub-Process ](#create-approval-sub-process-)
      - [Add Decision to Determine Approver List ](#add-decision-to-determine-approver-list-)
      - [Add Approver Form with Sales Order Items Table ](#add-approver-form-with-sales-order-items-table-)
    - [Add Condition ](#add-condition-)
    - [Add Action to read Sales Order Header ](#add-action-to-read-sales-order-header-)
    - [Add Action to Update Sales Order ](#add-action-to-update-sales-order-)
    - [Add Approval and Rejection Notifications ](#add-approval-and-rejection-notifications-)
- [Exercise 1 - Exercise 1 Description](#exercise-1---exercise-1-description)
  - [Exercise 1.1 Sub Exercise 1 Description](#exercise-11-sub-exercise-1-description)
  - [Exercise 1.2 Sub Exercise 2 Description](#exercise-12-sub-exercise-2-description)
  - [Summary](#summary)

## Overview <a name="overview"></a>

In this exercise you will learn:

- How to add an event trigger to a process
- How to add action to read sales order items
- How to create an approval sub-process
- How to add a condition
- How to add action to update sales order
- How to add confirmation and rejection notifications

### Add Event Trigger to Process <a name="eventTrigger"></a>

1. In the Lobby, select the three dots next to project **AD163 - XXX - Manage Billing Block in Sales Order**, then choose **Save as New Project**.

  ![02](./images//001.png)

2. In the **Save as New Project** pop-up:

  - Select **Editable version** as **Version**
  - Replace the XXX in the **Project Name** with your user name
  - Choose **Save as new**

  ![02](./images//002.png)

  Your project gets created in the Lobby.

3. Click on the newly created project.

  ![02](./images//003.png)

  In the **Overview** tab of your project, select **Create > Process**.
 
  ![02](./images//004.png)

4. In the **Create Process pop-up**:

  - Enter **Name:** Billing Block Removal Process
  - Enter **Description:** Process to update the billing block based on the Approval
  - Choose **Create**

  ![02](./images//005.png)

  The process gets added in the process builder.

5. Select the **+** next to the **Trigger** and then **Events > + New Event Trigger**

  ![02](./images//006.png)

6. In the **Create Event Trigger** pop-up:

  - Enter **Name:** SalesOrderBillingBlockStatusChanged
  - Select **Event Object:** Sales Order Events
  - Select **Event:** SalesOrder Billing Block Status Changed
  - Choose **Create**

  ![02](./images//007.png)

7. The Event Trigger gets created. Choose **OK**.

  ![02](./images//008.png)

8. In **General** tab of **Process Details**:
   
  - Enter **Subject:** Process to approve the removal of billing block and updating the sales order and select the Process Input **SalesOrder**
  - As **Business Key**, select the Process Input **SalesOrder**

9. Save your work.

  ![02](./images//009.png)

### Add Condition to match Sales Order <a name="matchSalesOrderCondition"></a>

1. In the Process Builder, select **+ > Controls > Condition**.
   
  ![02](./images//010.png)

2. Connect the outgoing flow of the Default branch to the End activity.

  ![02](./images//011.png)

3. Select the **Condition** control and perform the following:

  - Change the **Step Name** to sales order matches?
  - Change the **Branch Name** to yes.
  - Choose **Open Condition Editor** to define the Condition.

  ![02](./images//012.png)

4. In the **Edit Branch Condition**, set the condition:

  - Select Process Input SalesOrder
  - Select **is equal to**
  - Enter the number of the sales order you created in exercise 1
  - Choose **Apply**

  ![02](./images//013.png)

5. Save your work.

  ![02](./images//014.png)


### Add Action to read Sales Order Items <a name="actionReadSalesOrderItems"></a>

1. In the Process Builder, select the **+** next to the **yes** branch of the **sales order matches?** condition, then choose **Actions > Browse library**.
   
  ![02](./images//015.png)

2. In the **Browse library** pop-up, select the **Reads all items of a sales order** action from **Project: Sales Order** and choose **Add**.

  ![02](./images//016.png)

3. In the **General** section of the Action:

  - Change the **Step Name** to Reads Sales Order Items
  - Select the **Destination variable**: S4HANADestination

  ![02](./images//017.png)

4. In the **Inputs** section of the Action, select the **SalesOrder** Process Input.

5. Choose **Save**.

  ![02](./images//018.png)

  
### Create Approval Sub-Process <a name="approvalSubProcess"></a>

1. In the Process Builder, select the **+** next to the **Reads Sales Order Items** action and choose **Subprocesses > + New Process**.

  ![02](./images//019.png)

2. In The **Create Process** pop-up:
   
  - Enter **Name:** Approve Billing Block Removal
  - Enter **Description:** Process to modularize the approval process
  - Choose **Create**

  ![02](./images//020.png)

3. In the **General** section of the SubProcess, select **Edit Process**.

  ![02](./images//021.png)

  The SubProcess Builder will open.

4. In the **General** section:

  - Change the **Process name** to Modularize Approval Process
  - Change the **Subject** to SubProcess to approve changes to billing block in sales order

  ![02](./images//021a.png)

5. In the **Variables** section, under **Process Inputs**, choose **Configure**.

  ![02](./images//021b.png)

6. In the **Configure Process Inputs** pop-up:

  - Choose **Add Input**
  - Enter **Name:** SalesOrderInfo
  - Select **Type:** Sales Order
  - Choose **Apply**

  ![02](./images//021c.png)

  You have configured the Process Inputs. Now you will configure the Process Outputs.

7. Under **Process Outputs**, choose **Configure**.

  ![02](./images//021d.png)

8. In the **Configure Process Outputs** pop-up, you will add two inputs:

  - Choose **Add Output**
  - Enter **Name:** ApproverComments, select string as **Type** and check Required
  - Choose **Add Output** again
  - Enter **Name:** isApproved, select Boolean as **Type** and check Required
  - Choose **Apply**

  ![02](./images//021e.png)

9. Save your work.
    
#### Add Decision to Determine Approver List <a name="decisionDetermineApproverList"></a>

1. Select the **+** next to the Trigger, and choose **Decision > + New Decision**

  ![02](./images//022.png)

3. In the **Create Decision** pop-up:

  - Enter **Name:** Determine Approver
  - Enter **Description:** Determine approver based on sales order distribution channel and sold to party
  - Choose **Create**

  ![02](./images//023.png)

4. Choose **Save** and then **Edit Decision**.

  ![02](./images//024.png)

  The decision editor opens. You sill start configuring the input and output parameters that are needed to add rules to the decision.

5. Choose **Add Input Parameter**:

  - Enter **Name:** SalesOrderInput
  - Enter **Description:** Sales order details
  - Select **Type:** Sales Order

6. Choose **Add Output Parameter**:

  - Enter **Name:** ApproverOutput
  - Enter **Description:** Approver details
  - Select **Type:** Approver

7. Select the **Rules** tab.

  ![02](./images//025.png)

8. Choose **Add Rule**.

  ![02](./images//026.png)

9. In the **Create Rule** window, you will enter the Rule Details:

  - Select **Decision Table**
  - Enter **Rule Name:** Get Approver
  - Enter **Rule Description:** Rule to determine approver based on sales order information
  - Select **Hit Policy**: All Match
  - Choose **Next Step**

  ![02](./images//027.png)

10. Now you will configure the Conditions:

  - Under **Vocabulary > Input/Output**, select **SalesOrderInp > SoldToParty**
  - Select as **Operator:** =
  - Choose **Next Step**

  ![02](./images//028.png)

11. To configure the Results:

  - Under **Vocabulary**, select **ApproverOutput > Email**
  - Choose **Next Step**
  
  ![02](./images//029.png)

12. You may review your Decision Table and choose **Create**.

  ![02](./images//030.png)

13. Configure your Decision Table:

  - Under **SoldToParty =**, enter '17100001'
  - Under **Email**, enter your user such as 'AD163_046'
  - Choose **Save**

  ![02](./images//031.png)

  Now you need to map the decision to the process content.

14. Navigate back to the **Modularize Approval Process**, select the **Decision** and choose **Inputs** tab

  ![02](./images//032.png)

15. Under **SalesOrderInp**, map **DistributionChannel** to **Process Inputs > SalesOrderInfo > DistributionChannel**.
    
16. Under **SalesOrderItemDetails**, bind list to **Process Inputs > SalesOrderInfo > list SalesOrderItemDetails**.

  ![02](./images//033.png)

17. Under **SalesOrderInp**, map **SalesOrderNumber** to **Process Inputs > SalesOrderInfo > SalesOrderNumber**.
    
18. Under **SalesOrderInp**, map **SoldToParty** to **Process Inputs > SalesOrderInfo > SoldToParty**.

19. Save your work.

  ![02](./images//034.png)


#### Add Approver Form with Sales Order Items Table <a name="approverForm"></a>

1. In the SubProcess Builder, select the **+** next to the Decision and choose **Approvals > Approval Form**.

  ![02](./images//035.png)

2. Choose **Save** and then **Edit Form**.

  ![02](./images//036.png)

  The Form Builder opens. You will add a Sales Order Items Table.

3. Select a Table field and drag and drop it between **Billing Block Status (C=Blocked)** field and the checkbox.

  ![02](./images//037.png)

4. Perform the following actions:

  - Under **Items Details > Configuration**, check Read Only
  - Enter **New Table:** Items Details
  - Select the **+**
  - Select **Text** to add a new Text to the table.

  ![02](./images//038.png)

5. Enter **New Text:** Item and add a new Text.

  ![02](./images//039.png)

6. Enter **New Text:** Material and repeat step 5 to add two other Texts: ItemDescription and RequestedQuantity.
   
7. Save your form.

  ![02](./images//040.png)

8. Navigate back to the Modularize Approval Process.

7. Select the Approval Form. In the **General** section:

  - Enter **Subject:** Review and approve changes in billing block for sales order:
  - Under **Recipients**, map **Users** to **Determine Approver > ApproverOutput > Email**

  ![02](./images//041.png)

8. Go to the **Inputs** tab and map the inputs with the Process Content:

  - BillingBlockStatus to **Process inputs > SalesOrderInfo > BillingBlockStatus**
  - Distribution Channel to **Process inputs > SalesOrderInfo > DistributionChannel**
  - **Items Details > list - SalesOrderItemDetails** to **Process Inputs > list SalesOrderItemDetails**
  - Sales Order Number to **Process inputs > SalesOrderInfo > SalesOrderNumber**
  - Sold-To-Party to **Process inputs > SalesOrderInfo > SoldToParty**
  - Choose **Save**

  ![02](./images//042.png)

9. Connect the Reject node of the Approval Form to the End activity.
    
  ![02](./images//043.png)

  You will map the Process Outputs to the Process Content of the Approval Form.

10. Select the End activity.

  ![02](./images//044.png)

11. Map **Process Outputs > ApproverComments** to **Approval Form > Approver's Comment**
    
12. Map **Process Outputs > isApproved** to **Approval Form > Select the checkbox...**

13. Save your work.

  ![02](./images//045.png)

  Now that you you have created your Approval SubProcess you need to configure the inputs of the SubProcess with the Process Content.

14. Navigate back to the Billing Block Removal Process, select the Approval Billing Block Removal SubProcess and go to Inputs Tab.

  - Map **SalesOrderInfo > BillingBlockStatus** to **Process Inputs > data > OverallBillingBlockStatus**
  - Map **SalesOrderInfo > DistributionChannel** to **Process Inputs > data > DistributionChannel**
  - Map **SalesOrderItemDetails** to **Reads Sales Order Items > result > Collection of A_SalesOrderItemType > list results**
  
  ![02](./images//046.png)

  - Map **SalesOrderInfo > SalesOrderNumber** to **Process Inputs > data > SalesOrder**
  - Map **SalesOrderInfo > SoldToParty** to **Process Inputs > data > SoldToParty**
  - Choose **Save**

  ![02](./images//047.png)


### Add Condition <a name="condition"></a>

1. In the Process Builder, select **+** next to the SubProcess and choose **Controls > Condition**.

  ![02](./images//048.png)

2. In the Condition panel on the right:

  - Change the **Step Name:** is approved?
  - Change the **Branch Name:** to yes
  - Choose **Save** and **Open Condition Editor** to define the Condition

  ![02](./images//049.png)

3. In the **Edit Branch Condition** window:

  - Select Process Content **isApproved** from **Approve Billing Block Removal**
  - Select true
  - Choose **Apply**

  The Condition reads: if value of isApproved is equal to true.

  ![02](./images//050.png)

4. Connect the outgoing Default branch of the Condition to the End activity.

5. Choose **Save**.
   
   ![02](./images//050a.png)  


### Add Action to read Sales Order Header <a name="actionReadSalesOrderHeader"></a>

1. In the Process Builder, select **+** next to the yes branch of the Condition, then **Actions > Browse library**.

  ![02](./images//051.png)

2. In the **Browse library** pop-up, select **Reads the header of a sales order** action from **Project: Sales Order** and choose **Add**.
   
  ![02](./images//052.png)

3. In the **General** section of the Action:

  - Change the **Step Name:** Get ETAG for PATCH
  - Select the **Destination variable:** S4HANADestination

  ![02](./images//053.png)

4. Go to the **inputs** section of the Action and map **SalesOrder** to **Process Inputs > data > salesOrder**.

5. Choose **Save**.

  ![02](./images//054.png)


### Add Action to Update Sales Order <a name="actionUpdateSalesOrder"></a>

1. In the Process Builder, select **+** next to the Action and choose **Actions > Browse library**.
   
  ![02](./images//055.png)

2. In the **Browse library** pop-up, select **Updates a sales order** action from **Project: Sales Order** and choose **Add**.
   
  ![02](./images//056.png)

3. In the **General** section of the Action:

  - Change the **Step Name:** Updates a sales order
  - Select the **Destination variable:** S4HANADestination

  ![02](./images//057.png)

4. Go to the **Inputs** section of the Action and map **ifMatch** to **Get ETAG for Patch > result > Sales Order Header > metadata > etag**.

  ![02](./images//058.png)

5. Map **SalesOrder** to **Process Inputs > data > SalesOrder**

6. Choose **Save**.

  ![02](./images//059.png)


### Add Approval and Rejection Notifications <a name="approvalREjectionNotifications"></a>

1. In the Process Builder, select **+** next to the **Updates a sales order** Action and choose **Forms > Approval Notification**.

  ![02](./images//060.png)

2. In the **General** section of the Form:

  - Enter **Subject:** as **Removal of billing block is approved for sales order:** and map the Process Content: **Process Inputs > data > SalesOrder**
  - Under **Recipients > Users**, enter your user such as **AD163_046**

  ![02](./images//061.png)

3. Go to the **Inputs** section of the Form:

  - Map **Distribution Channel** to **Process Inputs > data > DistributionChannel**
  - Map **Sales Order Number** to **Process Inputs > data > SalesOrder**
  - Map **Sold-To-Party** to **Process Inputs > data > SoldToParty**
  - Choose **Save**

  ![02](./images//062.png)

  You will duplicate the **Approval Notification** Form in order to create your **Rejection Notification** Form.

4. Navigate to the **Overview** tab.

5. Select the three dots next to the **Approval Notification** then select **Duplicate**.
   
  ![02](./images//063.png)

6. In the **Duplicate Artifact** pop-up, enter as **Name:** Rejection Notification and choose **Duplicate**.

  ![02](./images//064.png)

  The Form Builder opens. Now, you will update your Rejection Notification to reflect rejection.

7. Change the **Headline** to: Billing Block Removal Rejected.
   
8. Drag and drop a **Paragraph** field after the Headline field and enter as **New Paragraph:** The request to remove the billing block on the sales order has been rejected. You can find the reason of rejection and the details of your the sales order below:
    
9. Drag ad drop a **Text Area** field after the Paragraph and enter as **New Text Area:** Reason for Rejection. 
    
10. Check Read Only as Configuration.

  ![02](./images//065.png)

11. Now drag and drop a **Paragraph** field after the **Text Area** and enter as **New Paragraph:** Your Sales Order Details:
    
12. Drag and drop a **Text** field after Distribution Channel. Enter as **New Text:** Billing Block Status.
    
13. Check Read Only as Configuration.
    
14. Save your Form.

  ![02](./images//066.png)

15. Navigate back to the **Billing Block Removal Process**. Select the **+** next to the DEfault branch of the **is approved?** Condition. Then choose **Forms > Rejection Notification**.

  ![02](./images//067.png)

16. In the **General** section of the Form:

  - Enter **Subject:** as **Removal of billing block is rejected for sales order:** and map the Process Content: **Process Inputs > data > SalesOrder**
  - Under **Recipients > Users**, enter your user such as **AD163_046**

  ![02](./images//068.png)

17. Go to the **Inputs** section of the Form:

  - Map **Billing Block Status** to **Process Inputs > data > OverallBillingBlockStatus**
  - Map **Distribution Channel** to **Process Inputs > data > DistributionChannel**
  - Map **Reason for Rejection** to **Approve Billing Block Removal > ApproverComments**
  - Map **Sales Order Number** to **Process Inputs > data > SalesOrder**
  - Map **Sold-To-Party** to **Process Inputs > data > SoldToParty**
  - Choose **Save**

  ![02](./images//069.png)











# Exercise 1 - Exercise 1 Description

In this exercise, we will create...

## Exercise 1.1 Sub Exercise 1 Description

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex1/images/01_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

