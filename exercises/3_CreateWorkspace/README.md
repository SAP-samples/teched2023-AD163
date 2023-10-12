# Create and design a Workspace Using SAP Build Work Zone, advanced edition
<!-- description --> Using SAP Build Work Zone, create a Workspace for your sales team to collaborate to manage Sales Orders.

 ## Prerequisites
- You integrated your process to your App.
- You have subscribed to SAP Build Work Zone, advanced edition and was assigned to the **Workzone_Admin** role.



## You will learn
- How to create and design a Workspace using SAP Build Work Zone, advanced edition.
- How to integrate backend apps to your Workspace.
- How to add cards to your Workspace.



## Intro
In this exercise, you will create and design your own business site using SAP Build Work Zone, advanced edition. You will integrate the application you developed using SAP Build Apps, and UI integration cards that are already deployed to the sub account.

The site you will design will have a space and a page.


### Open SAP Build Work Zone, advanced edition
Open the SAP Build Lobby from this link:  [SAP Build Lobby](https://ad163-hxj0v9xc.eu10.build.cloud.sap/lobby).

  - Follow this tutorial to access SAP Build Work Zone from the SAP Build Lobby: [Access SAP Build Work Zone from the SAP Build Lobby](https://developers.sap.com/tutorials/workzone-access-sap-build.html).

### Create and design your Workspace
Follow this tutorial to create and design your Sales Management Workspace:  [Add a Workspace to SAP Build Work Zone, advanced edition](https://developers.sap.com/tutorials/workzone-build-2-workspace.html).

### Integrate S/4HANA Cloud apps to your Workspace

In order to Integrate apps to Work Zone, you first need to configure them in the Content Manager of SAP Build Work Zone.
In this sub account, the apps are already configured for you, and you only need to add them to the UI.

To add the `apps` to the UI:
  1. Click the Pencil icon to edit your **Sales Order** workspace.

  ![App design](appDesign.jpg)


  2. Click the **+** icon to add a section below the third row.

  3. Click **Add Widget** on the newly added section and and select **Tiles**.

  4. Check the Create Sales Order,   and click **Add**.

  5. Click the cogwheel of this newly added section and add title **Apps**, and Top padding **30**.

  6. Click **Publish** to publish your work.


### Integrate cards to your Workspace


![Work Zone](/exercises/3_CreateWorkspace/images/0_std_open.jpg)


## Create and design your Workspace
Follow [this tutorial](https://developers.sap.com/tutorials/workzone-build-2-workspace.html) to create and design your workspace.

  1. Click **Create Site**.

  ![Work Zone](/exercises/3_CreateWorkspace/images/1_create_new_site.png)

  2. Enter JobCore<id> as the site name and click Create. <id> is a unique id you should use to identify your site.

## Summary

Now that you have created the created and designed your Workspace,
<br>Continue to - [Exercise 4 - Run Process](../4_RunProcess/README.md)
