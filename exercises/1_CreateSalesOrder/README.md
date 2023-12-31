# Exercise 1 - Create Sales Order

In this exercise, you will create a Sales Order by referring to an existing Sales Order. This Sales Order will not have a billing block. Please note down the Sales Order number generated at the end of the exercise. This is needed later for designing the process and end-to-end testing.

## Exercise

After completing these steps you will have a Sales Order number created without a billing block.

1.	Logon to the S/4HANA system
  <br>S/4HANA Cloud URL: https://my407161.s4hana.cloud.sap/ui
  <br>Username / Password: Login with your user id AD163_XXX where XXX is your assigned user like 001 or 002 and so on and the password will be Acce$$teched23

2. Search for va01 and click "Create Sales Order - VA01"
   <br>![](/exercises/1_CreateSalesOrder/images/VA01.png)

3.	Enter Order Type as “OR” and click on “Create with Reference”.
   <br>![](/exercises/1_CreateSalesOrder/images/EnterOR.png)

4. In the “Order” tab, enter Order as 3 and click on “Copy”.
   <br>![](/exercises/1_CreateSalesOrder/images/EnterSalesOrder.png)

5. In the “Review Availability Check” page, click “Apply”.
   <br>![](/exercises/1_CreateSalesOrder/images/ReviewAndApply.png)

6. In “Create Standard Order:Overview” page enter a customer reference text and note that the “Billing Block” is blank.
   <br>This means there is no billing block on the Sales Order.
   <br>![](/exercises/1_CreateSalesOrder/images/EnterCustomerReference.png)

7. Click “Save” and note down the Sales Order number. We will use this later while designing and executing the end-to-end process.
   <br>![](/exercises/1_CreateSalesOrder/images/SaveSalesOrder.png)



## Summary

Now that you have created the Sales Order,
Continue to - [Exercise 2 - Create Process](../2_CreateProcess/README.md)
