## Table of Contents
 - [Overview](#overview)
 - [Add Event Trigger](#eventTrigger)
 - [Create Approval Sub-Process](#approvalSubProcess)
 - [Add Condition](#addCondition)
 - [Add Action to Update Sales Order](#addCondition)
 - [Add confirmation and rejection notifications](#addNotifications)
 - [Summary](#summary)

### Overview <a name="overview"></a>

In this exercise you will learn:

- How to add an event trigger to a process
- How to create an approval sub-process
- How to add a condition
- How to add action to update sales order
- How to add confirmation and rejection notifications

## Event Trigger <a name="eventTrigger"></a>


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

