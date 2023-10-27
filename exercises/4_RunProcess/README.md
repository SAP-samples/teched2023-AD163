# Exercise 4 - Run Process

In this exercise, we will update the Sales Order that was created and add a billing reason to block the Sales Order for billing. The required event is dispatched from SAP S/AHANA and the process in SAP Build Process Automation is triggered. User approves the billing block removal via an approval form and the billing block in removed in  SAP S/4HANA.

## Exercise 4.1 Access your business site on runtime
As a Sales Management team member, you work and collaborate using SAP Build Work Zone, and specifically, using the Workspace your created.

To access the Workspace on runtime:
1. navigate to Work Zone runtime by clicking on this URL: https://ad163-hxj0v9xc.workzone.cfapps.eu10.hana.ondemand.com/site#workzone-home 

2. From the Work Zone homepage, click on Workspaces and select the Workspace you created
<br>![](/exercises/4_RunProcess/images/runtime-2.png)

3. Your Sales Management Workspace should look like this
<br>![](/exercises/4_RunProcess/images/runtime-3.png)

4. You may want to get advice from your colleagues , click Ask a Question and post your question.
<br>![](/exercises/4_RunProcess/images/runtime-4.png)

5.  You can also scroll to view the cards you added, notice that when you click on the items on the first card, it filters data on the second one
<br>![](/exercises/4_RunProcess/images/runtime-5.png)

6. To update a Sales Order, launch the Change Sales Order (VA02) app from your Workspace
<br>![](/exercises/4_RunProcess/images/runtime-6.png)   

## Exercise 4.2 Change Billing Block Status in S/4HANA
After completing these steps you will have chaned the billing block status for the Sales Order.

1. Enter Order as the Sales Order number that was created in “Create Sales Order” exercise and click on “Continue”.
<br>![](/exercises/4_RunProcess/images/EnterSOToEdit.png)

2. In the “Sales” tab, enter Billing Block as any value from the drop down and “Save”. Note: The sales order is blocked only when any of the reasons are selected.
<br>![](/exercises/4_RunProcess/images/UpdateBillingBlock.png)

3. Check the confirmation that the Sales Order was saved.
<br>![](/exercises/4_RunProcess/images/ConfirmUpdateSO.png)

Note: Now the event “Billing block status changed” will be triggered from SAP S/4HANA which will trigger the process that is created in SAP Build Process Automation.

## Exercise 4.3 Monitor Process

1.	Login to the [SAP Build Lobby](https://ad163-hxj0v9xc.eu10.build.cloud.sap/lobby) 

<br>Please use the Username / Password provided to you (Example : **AD163_047 , Acce$$teched23**)
<br>![](/exercises/4_RunProcess/images/Monitor01.png)

3.	Click on “Monitor” and then click on “Process Workflow and Instances”.<br>
<br>![](/exercises/4_RunProcess/images/Monitor02.png)

4.	All the processes are listed in the logs. Search for your project by giving your user name(example AD163_000) in Project and select your Project.<br>
<br>![](/exercises/ex2/4_RunProcess/Monitor03.png)

5.	Click on the instance with Running status to view the details of the logs<br>
<br>![](/exercises/ex2/4_RunProcess/Monitor04.png)

6.	Check that event trigger has started the process from the Context section<br>
<br>![](/exercises/ex2/4_RunProcess/Monitor05.png)

7.	Check the rest of the steps in the Logs section<br>
<br>![](/exercises/ex2/4_RunProcess/Monitor06.png)

## Exercise 4.4 Approves Sales Order Update from Inbox

1. Click on “My Inbox” icon on the top right to approve the  task.
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	Submit and check the status in S/4HANA.

## Exercise 4.5 View updated billing

1. Click on Display Sales Order (VA03) from your Workspace
<br>![](/exercises/4_RunProcess/images/view-1.png)

   
## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
