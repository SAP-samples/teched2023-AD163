# Create Sales Order

In this exercise, you will create a Sales Order by referring to an existing Sales Order. This Sales Order will not have a billing block. Please note down the Sales Order number generated at the end of the exersice. This is needed later for designing the process and end-to-end testing.

## Exercise

After completing these steps you will have a Sales Order number created without a billing block.

1.	Logon to the S/4HANA system
   S/4HANA Cloud URL: https://my407161.s4hana.cloud.sap/ui
   Username / Password: Provided to you (Example : AD-***@education.cloud.sap , ******)

2. Search for va01 and click "Create Sales Order - VA01"
   <br>![](/exercises/1_CreateSalesOrder/images/00_00_0010.png)

3.	Insert this code.
4.	<br>![](/exercises/ex0/images/00_00_0010.png)
``` abap
 DATA(params) = request->get_form_fields(  ).
 READ TABLE params REFERENCE INTO DATA(param) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.
```

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
