![image](https://github.com/SAP-samples/teched2023-AD163/assets/34297037/63af953e-e217-41d8-8753-bd25de93c7f4)[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2023-AD163)](https://api.reuse.software/info/github.com/SAP-samples/teched2023-AD163)
# AD163 - Extend Your Sales Order Process in SAP S/4HANA with SAP Build

## Description

This repository contains the material for the SAP TechEd 2023 session called **AD163 - Extend Your Sales Order Process in SAP S/4HANA with SAP Build**. 

**Billing block** is applied in Sales Order by internal sales representatives to prevent invoice being created in case of sales returns. These billing blocks need to be updated or deleted in random or on-demand fashion and is time critical activity in Order-to-Cash process. In many organisation this process is still manual where internal sales representatives get billing block change requests in form of Excel or Email attachment. Sales representatives download these attachments and then sales orders are manually updated in the S/4HANA system based on data in the excel files or attachments.


## Overview

This session introduces attendees how to modify or extend standard business processes from SAP S/4HANA. Leveraging SAP Build Process Automation and SAP Work Zone, advanced edition services of SAP Build portfolio to enhance the experience of managing billing block status change in SAP S/4HANA cloud. 

<img width="1145" alt="image" src="https://github.com/SAP-samples/teched2023-AD163/assets/34297037/dc3d166f-cf68-4d08-ab81-09c0a0e3e782">


In this scenario: <br>
- Sales order is created in SAP S/4HANA
- Billing block is updated in the sales order
- Billing Block Status Changed event is thrown by SAP S/4HANA
- SAP Event Mesh is configured to listen and communicate events 
- Process is triggered to approve the changes in SAP Build Process Automation
- Sales Order (A2X) API is used to get and patch sales order details in the backend system
- SAP Work Zone workspace is used to provide centralized access to S/4HANA applications, and workflow inbox applications
- Finally, sales representative is informed once the sales orders are updated
- In addition, whole process can be managed and monitored using out-of-the-box visibility.
    

## Requirements

There are no dedicated requirement for this exercise. But in case you want to gain some further knowledge around SAP Build, please feel free to attend these SAP TechEd workshops:
- Learn how to build a application, automate process and connect with CAP services in [AD272 - SAP Cloud Application Programming Model Meets SAP Build](https://github.com/SAP-samples/teched2023-AD272)
- Learn how to build a process and integrate with SAP and non-SAP systems [IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR](https://github.com/SAP-samples/teched2023-IN264)

## Exercises

- [Exercise 1 - Create and Configure Sales Order](exercises/ex1/)
- [Exercise 2 - Create Process](exercises/ex2/)
    - [Exercise 2.1 - Add Event Trigger](exercises/ex2#exercise-21-sub-exercise-1-description)
    - [Exercise 2.2 - Create Approval Sub-Process](exercises/ex2#exercise-22-sub-exercise-2-description)
    - - [Exercise 2.2.1 - Add API Trigger with Input and Output](exercises/ex2#exercise-22-sub-exercise-2-description)
    - - [Exercise 2.2.2 - Add Decision to Determine Approver List](exercises/ex2#exercise-22-sub-exercise-2-description)
    - - [Exercise 2.2.3 - Add Approver Form with Sales Order Items Table](exercises/ex2#exercise-22-sub-exercise-2-description)
    - [Exercise 2.3 - Add Condition](exercises/ex2#exercise-22-sub-exercise-2-description)
    - [Exercise 2.4 - Add Action to Update Sales Order](exercises/ex2#exercise-22-sub-exercise-2-description)
    - [Exercise 2.5 - Send Email Notification](exercises/ex2#exercise-22-sub-exercise-2-description)
- [Exercise 3 - Run Process](exercises/ex3/)
    - [Exercise 3.1 - Change Billing Block Status in S/4HANA](exercises/ex3#exercise-31-sub-exercise-1-description)
    - [Exercise 3.2 - Monitor Process](exercises/ex3#exercise-32-sub-exercise-2-description)
    - [Exercise 3.3 - Approves Sales Order Update from Inbox](exercises/ex3#exercise-33-sub-exercise-3-description)
  

## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2023 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
