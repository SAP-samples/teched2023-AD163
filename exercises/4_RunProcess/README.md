# Test end to end process

In this exercise, we will update the Sales Order that was created and add a billing reason to block the Sales Order for billing. The required event is dispatched from SAP S/AHANA and the process in SAP Build Process Automation is triggered. User approves the billing block removal via an approval form and the billing block in removed in  SAP S/4HANA.

## Exercise 2.1 Change Billing Block Status in S/4HANA

After completing these steps you will have created...

1. Logon to the S/4HANA system
<br>S/4HANA Cloud URL: https://my407161.s4hana.cloud.sap/ui
<br>Username / Password: Provided to you (Example : AD-***@education.cloud.sap , ******)

2.	Search for va02 and click "Change Sales Order - VA02"
<br>![](/exercises/4_RunProcess/images/VA02.png)

3. Enter Order as the Sales Order number that was created in “Create Sales Order” exercise and click on “Continue”.
<br>![](/exercises/4_RunProcess/images/EnterSOToEdit.png)

4. In the “Sales” tab, enter Billing Block as any value from the drop down and “Save”. Note: The sales order is blocked only when any of the reasons are selected.
<br>![](/exercises/4_RunProcess/images/UpdateBillingBlock.png)

5. Check the confirmation that the Sales Order was saved.
<br>![](/exercises/4_RunProcess/images/ConfirmUpdateSO.png)

Note: Now the event “Billing block status changed” will be triggered from SAP S/4HANA which will trigger the process that is created in SAP Build Process Automation.

## Exercise 2.2 Monitor Process

After completing these steps you will have...

1.	Login to the SAP Build Lobby 
<br>URL : https://ad163-hxj0v9xc.eu10.build.cloud.sap/lobby
<br>Username / Password : Provided to you (Example : AD-***@education.cloud.sap , ******)
<br>![](/exercises/4_RunProcess/images/Monitor01.png)

3.	Click on “Monitor” and then click on “Process Workflow and Instances”.
<br>![](/exercises/4_RunProcess/images/Monitor02.png)

4.	All the processes are listed in the logs. Search for your project / definition using the appropriate filters:
<br>![](/exercises/ex2/4_RunProcess/Monitor03.png)

5.	Click on the instance with Running status to view the details of the logs
<br>![](/exercises/ex2/4_RunProcess/Monitor04.png)

6.	Check that event trigger has started the process from the Context section
<br>![](/exercises/ex2/4_RunProcess/Monitor05.png)

7.	Check the rest of the steps in the Logs section
   


## Exercise 2.3 Approves Sales Order Update from Inbox
After completing these steps you will have created...

1. Click on “My Inbox” icon on the top right to approve the  task.
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	Submit and check the status in S/4HANA.


## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
