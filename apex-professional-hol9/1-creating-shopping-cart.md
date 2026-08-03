# Add Validations and Processes to the Shopping Cart Page

## Introduction

<<<<<<< HEAD

This Hands-on Lab is a collection of six tasks. After completing this lab, your application will enable customers to:

- Create validations on the Page Items.
- Create a Page process to create the Order
- Clear the shopping cart
- Proceed to checkout
=======
This lab enhances a shopping cart page by adding critical validations, processes, and branching processes to manage customer orders effectively. By the end, customers can place orders seamlessly, validate required information, clear their cart, and quickly proceed to checkout. These tasks ensure the application runs smoothly and delivers an optimized user experience.
>>>>>>> upstream/main

Estimated Time: 15 minutes

### Objectives

In this lab, you will:

- Create validations to ensure required fields are filled.

- Implement processes to create orders and manage the shopping cart.

- Add branching logic to efficiently transition between pages.

- Clear the shopping cart and proceed to checkout seamlessly.

### Downloads

Stuck or Missed out on completing the previous labs? Don't worry! First, follow the steps described in the following workshops:

- **[Get Started with Oracle APEX](https://livelabs.oracle.com/pls/apex/r/dbpm/livelabs/run-workshop?p210_wid=3509)**

- **[Using SQL Workshop > Lab 1: Install Sample Tables](https://livelabs.oracle.com/pls/apex/r/dbpm/livelabs/run-workshop?p210_wid=3524)**

- After installing the sample dataset tables, import the SQL script from **[here](https://c4u04.objectstorage.us-ashburn-1.oci.customer-oci.com/p/EcTjWk2IuZPZeNnD_fYMcgUhdNDIDA6rt9gaFj_WZMiL7VvxPBNMY60837hu5hga/n/c4u04/b/livelabsfiles/o/labfiles%2FOnlineShoppingApp-PartialDDLs.sql)**.

- Now import **[Online Shopping Application](https://c4u04.objectstorage.us-ashburn-1.oci.customer-oci.com/p/EcTjWk2IuZPZeNnD_fYMcgUhdNDIDA6rt9gaFj_WZMiL7VvxPBNMY60837hu5hga/n/c4u04/b/livelabsfiles/o/labfiles%2FCreatingApplicationPageControls-OnlineShoppingApplication.sql)** in your workspace.

- When you run the application, you may encounter an “unauthorized user” error because no user has been assigned to the authorization scheme yet. To fix this, go to **Shared Components** in your workspace. Under Security, select **Application Access Control**, and click **Add User Role Assignment**. Then, add the same username you use to log in to the workspace, choose the appropriate application role, and click **Create Assignment**.

- If you want to uninstall the database objects, run the  script from **[here](https://c4u04.objectstorage.us-ashburn-1.oci.customer-oci.com/p/EcTjWk2IuZPZeNnD_fYMcgUhdNDIDA6rt9gaFj_WZMiL7VvxPBNMY60837hu5hga/n/c4u04/b/livelabsfiles/o/labfiles%2FCleanup-Scripts.sql)**.

## Task 1: Create Validations on the Page

<<<<<<< HEAD
1. Navigate to the **App Builder**.

    ![Click App Builder](./images/click-app-builder.png " ")

2. Then Click on **Online Shopping Application**.

    ![Select Online Shopping Cart App](./images/click-app-builder1.png " ")
=======
In this task, you will add validations to ensure that required fields on the shopping cart page—such as customer name, email, and store—are filled before proceeding to the next steps. If mandatory information is missing, these validations will prompt the user with appropriate error messages.

1. Navigate to the **App Builder**.
>>>>>>> upstream/main

    ![Click App Builder](./images/click-app-builder.png " ")

<<<<<<< HEAD
    ![Navigate to Shopping Cart Page](./images/navigate-to-shopping-cart-page.png " ")
=======
2. Click **Online Shopping Application**.
>>>>>>> upstream/main

    ![Select Online Shopping Cart App](./images/click-app-builder1.png " ")

3. Select **17 - Shopping Cart** page.

<<<<<<< HEAD
     ![Create a Validation](./images/create-validation1.png " ")  
=======
    ![Navigate to Shopping Cart Page](./images/navigate-to-shopping-cart-page.png " ")
>>>>>>> upstream/main

4. Navigate to **Processing** tab. Right-click **Validating** and select **Create Validation**.

<<<<<<< HEAD
    ![Customise Validation](./images/create-validation2.png " ")
=======
    ![Navigate to Shopping Cart Page](./images/create-validation.png " ")
>>>>>>> upstream/main

5. In the property editor, enter/select the following:

    - Identification > Name: **Validate Name**

    - Under Validation:

<<<<<<< HEAD
     ![Customise Validation](./images/create-validation3.png " ")
=======
        - Type: **Item is NOT NULL**
>>>>>>> upstream/main

        - Item: **P17\_CUSTOMER\_FULL_NAME**

    - Under Error:

<<<<<<< HEAD
     ![Customise Validation](./images/create-validation4.png " ")       

## Task 2: Add a Process to Create the Order

1. On the **Processing** tab (left pane).
2. Right- click **Processing** and click **Create Process**.

     ![Create Page Process](./images/create-process1.png " ")

3. In the Property Editor, enter the following:
  Under Identification:
    - For Name - enter **Checkout**
    - For Type, Select **Invoke API**

  Under Settings, select what Process Executes:
    - For Type, Select **PL/SQL Package**
    - For Package, Enter the case-sensitive PL/SQL package name, **MANAGE_ORDERS**. You can type in the name or pick from the list.
    - For Procedure or Function, Enter the case-sensitive procedure or function name, **CREATE_ORDER**,  defined in the selected PL/SQL package. You can type in the name or pick from the list.

     ![Create and Configure Invoke API Process](./images/create-process2.png " ")  
=======
        - Error Message: **Please enter your name.**

        - Associated Item: **P17\_CUSTOMER\_FULLNAME**

    - Server-side Condition > When Button Pressed: **Proceed**

    ![Navigate to Shopping Cart Page](./images/create-validation11.png " ")

6. Create two more validations for the following items: **Email** and **Store**.

    | Name           | Validation > Type | Validation > Item       | Error Message                      | Associated Item         | Server-side Condition > When Button Pressed |
    | -------------- | ----------------- | ----------------------- | ------------------------------- |----------------------- | ------------- |
    | Validate Email | Item is NOT NULL  | P17\_CUSTOMER\_EMAIL    | Please enter your email address | P17\_CUSTOMER\_EMAIL    | Proceed |
    | Validate Store | Item is NOT NULL  | P17_STORE               | Please select a store           | P17_STORE               | Proceed |
    {: title="Validation Properties"}

    ![Customize Validation](./images/create-validation3.png " ")

    ![Customize Validation](./images/create-validation4.png " ")

## Task 2: Add a Process to Create the Order

This task focuses on creating a backend process that allows users to submit their orders. You will invoke a PL/SQL package that handles order creation, ensuring the order is successfully placed with all relevant customer information.

1. Navigate to **Processing** tab (left pane). Right-click **Processing** and select **Create Process**.

    ![Create Page Process](./images/create-process1.png " ")

2. In the Property Editor, enter/select the following:
    - Under Identification:
>>>>>>> upstream/main

        - Name: **Checkout**

<<<<<<< HEAD

4. On the **Processing** tab (left pane), Expand the Process **Checkout**. Under **Parameters**, Click **p_customer**.
   Under **Property Editor**, enter the following:
   Under Value :
   - For Type: Select **Item**
   - For Value: Select **P16_CUSRTOMER_FULLNAME**

  ![Configure Invoke API Process](./images/create-invoke-api1.png " ")

5. Repeat the Above steps for the other parameters **p_customer_email**,**p_store**,**p_order_id**,**p_customer_id**. Set the Item Names as follows.
    | Parameter Name  | When Button Pressed |
    | ---   |  --- |
    | p_customer_email | P16_CUSTOMER_EMAIL |
    | p_store | P16_STORE |
    | p_order_id | P16_ORDER_ID |   
    | p_customer_id | P16_CUSTOMER_ID |

    ![Configure Invoke API Process](./images/create-invoke-api2.png " ")


6. Click **Save**.

## Task 3: Add Process to Clear the Shopping Cart

1. On the **Processing** tab (left pane).
2. Right-click **Processing** and click **Create Process**.

    ![Create Page Process](./images/create-process12.png " ")

3. In the property editor,
    Under Identification:
      - For Name - Enter **Clear Shopping Cart**.
      - For Type - Select **Execution Chain**.
      - For Execution Chain - This attribute enables support for nested execution chains. Use this attribute to define another execution chain as the parent for this chain. For this example, select None.

    Under Settings:
      - Set **Run in Background** to **Yes**.

    ![Create and Configure Background Process](./images/create-background-process1.png " ")

4. Now, create a child process. In the Processing tab, select the Execution Chain process, right-click and select Create Child Process. The new child process displays under Processes.

    ![Create a Child Process](./images/create-child-process1.png " ")

5. In the Property Editor, enter the following:
  Under Identification:
    - For Name - enter **Clear shopping Cart - Child**
    - For Type, Select **Invoke API**

  Under Settings, select what Process Executes:
    - For Type, Select **PL/SQL Package**
    - For Package, Enter the case-sensitive PL/SQL package name, **MANAGE_ORDERS**. You can type in the name or pick from the list.
    - For Procedure or Function, Enter the case-sensitive procedure or function name, **CLEAR_CART**,  defined in the selected PL/SQL package. You can type in the name or pick from the list.

     ![Configure Child Process](./images/create-child-process2.png " ")

Click Save.

=======
        - Type: **Invoke API**

    - Under Settings:

        - Type: **PL/SQL Package**

        - Package: **MANAGE_ORDERS**.  You can type in the name or pick from the list.

        - Procedure or Function: **CREATE_ORDER**,  defined in the selected PL/SQL package. You can type in the name or pick from the list.

    ![Create and Configure Invoke API Process](./images/create-process2.png " ")

3. Expand the **Checkout** process. Under **Parameters**, select **p_customer** and enter/select the following:

    - Under Value:

        - Type: **Item**

        - Value: **P17\_CUSTOMER\_FULLNAME**

    ![Configure Invoke API Process](./images/create-invoke-api.png " ")

4. Click **Save**.

## Task 3: Add Process to Clear the Shopping Cart

In this task, you will create a process to clear the shopping cart when the customer requests it. This includes providing a success message and redirecting the user to the shopping cart page, ensuring they can start fresh.

1. In the **Processing** tab, right-click **Ajax Callback** and select **Create Process**.

    ![Create Page Process](./images/create-process12.png " ")

2. In the property editor, enter/select the following:

    - Identification > Name: **clear_cart**

    - Source > PL/SQL Code: Copy and paste the below code:

        ```
       <copy>
        BEGIN
            manage_orders.clear_cart;
        END;
        ```

        </copy>

    - Success Message > Success Message: **Your cart has been successfully cleared**

    - Server-side Condition > When Button Pressed: **Clear**

    ![Create and Configure Background Process](./images/clear-cart.png " ")

3. Under **Rendering** tab, select **Proceed**. In the Property Editor, under **Behavior**, enable **Show Processing**.

    This would avoid accidental multiple-page submissions by displaying a processing animation and temporarily disabling page interaction using the new Show Processing attribute available for page buttons.

    ![Configure Child Process](./images/button-processing.png " ")

4. Click **Save**.

5. Navigate to **Shared Components**.

    ![Configure Child Process](./images/user-interface.png " ")

6. Under **User Interface**, click **User Interface Attributes**.

    ![Configure Child Process](./images/auto-dismissing.png " ")

7. Under **Attributes**, enable **Auto Dismiss Success Messages** and click **Apply Changes**.

    By turning this new application's User Interface attribute on, all success messages in the application will be dismissed automatically.

    Also, you can use the new **setDismissPreferences** API to control dismiss preferences and customize the timing of the auto-dismiss functionality.

    ![Configure Child Process](./images/shared-comp.png " ")
>>>>>>> upstream/main

## Task 4: Add Branches to the Page

In this task, you will create a branching process that redirects the user to the appropriate page after they submit an order. Branches ensure a smooth navigation experience by guiding users based on their actions, such as checking or viewing their order details.

<<<<<<< HEAD
     ![Create a Branch](./images/create-branch1.png " ")  
=======
1. In the top right corner, navigate to **Edit Page 17**.
>>>>>>> upstream/main

    ![Navigate to page 17](./images/17-page.png " ")

2. In the **Processing** tab (left pane), right-click **After Processing** and select **Create Branch**.

    ![Create a Branch](./images/create-branch1.png " ")

3. In the Property Editor, enter/select the following:

    - Identification > Name: **Go to Orders**

    - Target: Click **No Link Defined**.

<<<<<<< HEAD
    ![Configure Branch](./images/create-branch2.png " ")

4. Create a  second branch when the user clears the shopping cart. Right-click on **After Processing** and click **Create Branch**.
=======
        - Type: **Page in this application**

        - Page: **16**
>>>>>>> upstream/main

        - Set Items: Enter/select the following:

            | Name           | Value            |
            | -------------- | ---------------- |
            | P16\_ORDER | &P17\_ORDER\_ID. |
            {: title="List of Taregt Item(s)"}

        - Clear Cache: **16**.

<<<<<<< HEAD
    ![Configure Branch](./images/create-branch3.png " ")

  Click Save.

## Summary

In this hands-on lab, You learned to create data validations for page items, ensuring data accuracy. You also implemented a dedicated page process to streamline order creation. Additionally, the lab covered clearing the shopping cart and enabling a seamless transition to the checkout process, enhancing the overall user experience.  You may now **proceed to the next lab**.

## Whats Next:

In the next lab, you explore the use of Dynamic Actions to efficiently manage the shopping cart, allowing for real-time updates. Additionally, you learn how to review product details and enabling users to add, edit, or remove items from their cart with the help of Page Process.
=======
        Click **OK**.

    - Server-side condition > When Button Pressed: **Proceed**.

    ![Configure Branch](./images/create-branch.png " ")

4. Click **Save**.

## Summary

In this hands-on lab, you learned to create data validations for page items, ensuring data accuracy. You also implemented a dedicated page process to streamline order creation. Additionally, the lab covered clearing the shopping cart and enabling a seamless transition to the checkout process, enhancing the overall user experience. You may now **proceed to the next lab**.
>>>>>>> upstream/main

## What's Next

<<<<<<< HEAD
- **Author** - Roopesh Thokala, Senior Product Manager
- **Contributor** - Ankita Beri, Product Manager
- **Last Updated By/Date** - Roopesh Thokala, Senior Product Manager, October 2023
=======
In the next lab, you explore the use of Dynamic Actions to manage the shopping cart, allowing for efficient real-time updates. Additionally, you learn how to review product details and enable users to add, edit, or remove items from their cart with the help of Page Process.

## Acknowledgements

- **Author** - Roopesh Thokala, Senior Product Manager; Ankita Beri, Product Manager
- **Last Updated By/Date** - Ankita Beri, Product Manager, September 2024
>>>>>>> upstream/main
