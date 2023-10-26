[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2023-AD163)](https://api.reuse.software/info/github.com/SAP-samples/teched2023-AD163)

# AD163 - Extend Your Sales Order Process in SAP S/4HANA with SAP Build

## Description

This repository contains the material for the SAP TechEd 2023 session called **AD163 - Extend Your Sales Order Process in SAP S/4HANA with SAP Build**. 

**Billing block** is applied in Sales Order by internal sales representatives to prevent invoice being created in case of sales returns. These billing blocks need to be updated or deleted in random or on-demand fashion and is time critical activity in Order-to-Cash process. In many organisation this process is still manual where internal sales representatives get billing block change requests in form of Excel or Email attachment. Sales representatives download these attachments and then sales orders are manually updated in the S/4HANA system based on data in the excel files or attachments.


## Overview

<img width="1145" alt="image" src="https://github.com/SAP-samples/teched2023-AD163/blob/main/exercises/4_RunProcess/images/SAP-Build-low-code.jpeg">  




This session introduces attendees how to modify or extend standard business processes from SAP S/4HANA. Leveraging SAP Build Process Automation and SAP Build Work Zone, advanced edition services of SAP Build solutions to enhance the experience of managing billing block status change in SAP S/4HANA cloud. 

<img width="1145" alt="image" src="https://github.com/SAP-samples/teched2023-AD163/assets/34297037/dc3d166f-cf68-4d08-ab81-09c0a0e3e782">


In this scenario: <br>
- Sales order is created in SAP S/4HANA
- Billing block is updated in the sales order
- Billing Block Status Changed event is thrown by SAP S/4HANA
- SAP Event Mesh is configured to listen and communicate events 
- Process is triggered to approve the changes in SAP Build Process Automation
- Sales Order (A2X) API is used to get and patch sales order details in the backend system
- SAP Build Work Zone workspace is used to provide centralized access to S/4HANA applications, workflow inbox applications, and other web content
- Finally, sales representative is informed once the sales orders are updated
- In addition, whole process can be managed and monitored using out-of-the-box visibility.
    

## Requirements

There are no dedicated requirement for this exercise. But in case you want to gain some further knowledge around SAP Build, please feel free to attend these SAP TechEd workshops:
- Learn how to build a application, automate process and connect with CAP services in [AD272 - SAP Cloud Application Programming Model Meets SAP Build](https://github.com/SAP-samples/teched2023-AD272)
- Learn how to build a process and integrate with SAP and non-SAP systems [IN264 - Combine SAP Integration Suite and SAP Build Process Automation in HR](https://github.com/SAP-samples/teched2023-IN264)

## Exercises

- [Exercise 1 - Create and Configure Sales Order](exercises/1_CreateSalesOrder/)
- [Exercise 2 - Create Process](exercises/2_CreateProcess/)
    - [Exercise 2.1 - Add Event Trigger to Process](exercises/2_CreateProcess#exercise-21---add-event-trigger-to-process-)
    - [Exercise 2.2 - Add Condition to Match Sales Order](exercises/2_CreateProcess#exercise-22---add-condition-to-match-sales-order-)
    - [Exercise 2.3 - Add Action to Read Sales Order Items](exercises/2_CreateProcess#exercise-23---add-action-to-read-sales-order-items-)
    - [Exercise 2.4 - Create Approval Sub-Process](exercises/2_CreateProcess#exercise-24---create-approval-sub-process-)
      - [Exercise 2.4.1 - Add Decision to Determine Approver List](exercises/2_CreateProcess#exercise-241---add-decision-to-determine-approver-list-)
      - [Exercise 2.4.2 - Add Approver Form with Sales Order Items Table](exercises/2_CreateProcess#exercise-242---add-approver-form-with-sales-order-items-table-)
    - [Exercise 2.5 - Add Condition](exercises/2_CreateProcess#exercise-25---add-condition-)
    - [Exercise 2.6 - Add Action to Read Sales Order Header ](exercises/2_CreateProcess#exercise-26---add-action-to-read-sales-order-header-)
    - [Exercise 2.7 - Add Action to Update Sales Order](exercises/2_CreateProcess#exercise-27---add-action-to-update-sales-order-)
    - [Exercise 2.8 - Add Approval and Rejection Notifications](exercises/2_CreateProcess#exercise-28---add-approval-and-rejection-notifications-)
    - [Exercise 2.9 - Release and Deploy the Process](exercises/2_CreateProcess#exercise-29---release-and-deploy-the-process-)
- [Exercise 3 - Create a Workspace With Apps, Information, and Processes for Sales Management](exercises/3_CreateWorkspace/)
    - [Exercise 3.1 - Design a Workspace for Sales Management](exercises/3_CreateWorkspace#exercise-41-sub-exercise-1-description)
    - [Exercise 3.2 - Integrate Apps and Cards to your Workspace](exercises/3_CreateWorkspace#exercise-42-sub-exercise-2-description)
    - [Exercise 3.3 - Experience improved Sales collaboration by accessing your Workspace, view data, run apps and Approves Sales Orders from Inbox](exercises/3_CreateWorkspace#exercise-43-sub-exercise-3-description)
- [Exercise 4 - Run Process](exercises/4_RunProcess/)
    - [Exercise 4.1 - Change Billing Block Status in S/4HANA](exercises/ex3#exercise-31-sub-exercise-1-description)
    - [Exercise 4.2 - Monitor Process](exercises/ex3#exercise-32-sub-exercise-2-description)
    - [Exercise 4.3 - Approves Sales Order Update from Inbox](exercises/ex3#exercise-33-sub-exercise-3-description)
  
  

## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2023 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
