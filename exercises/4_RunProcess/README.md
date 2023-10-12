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


## Exercise 2.2 Monitor Process

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)
## Exercise 2.3 Approves Sales Order Update from Inbox
After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
