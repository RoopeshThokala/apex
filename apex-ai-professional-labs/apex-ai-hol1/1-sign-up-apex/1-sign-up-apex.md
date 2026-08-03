# Provision an APEX Workspace

## Introduction

Oracle APEX is an enterprise AI application platform for building secure, scalable web and mobile applications. Trusted by thousands of organizations, APEX powers systems that run core business operations every day. With Oracle AI Database and Oracle Cloud Infrastructure, every application inherits built-in reliability, governance, and security. APEX helps developers turn ideas into production-ready apps quickly, without sacrificing control or performance. To start, you will need to decide on the service you are going to use for this workshop and then create an APEX Workspace accordingly.

If you already have an Oracle APEX 26.1 Workspace provisioned, you can skip this lab.

Estimated Time: 5 minutes
<!--
Watch the video below for a quick walk through of the lab.

[](youtube:RcSCnZnDzDE)
-->

### What is an APEX Workspace?

An APEX Workspace is a logical domain where you define APEX applications. Each Workspace is associated with one or more database schemas (database users) which are used to store the database objects, such as tables, views, packages, and more. APEX applications are built on top of these database objects.

### How Do I Find My APEX Release Version?

To determine which release of Oracle APEX you are currently running, do one of the following:

- View the release number on the Workspace home page:

  - Sign in to Oracle APEX. The Workspace home page appears. The current release version is displayed in the bottom right corner.

    ![Workspace home page](./images/release-number.png " ")

    ![APEX Release Number](./images/release-number2.png " ")

- View the about APEX page:

  - Sign in to Oracle APEX. The Workspace home page appears.

  - Select the help menu at the bottom-left of the page and select **About**. The About APEX page appears.

    ![APEX Details](images/version.png)

### Where to Run the Lab

You can run this lab in any Oracle Database with APEX 26.1 installed. This includes the APEX Application Development Service, the free, "Development Only" apex.oracle.com service, your on-premises Oracle Database (providing APEX 26.1 is installed), on a third-party cloud provider where APEX 26.1 is installed, or even on your laptop by installing Oracle XE or Oracle VirtualBox App Dev VM and installing APEX 26.1.

The following steps show how to sign up for an **APEX Application Development** service, an **Oracle Autonomous AI Database** cloud service, or the **oracleapex.com** service.

- The **oracleapex.com** service is also free, but it is designated only for development purposes. Running production apps is not allowed. You can use any of these options for this workshop.

- The **Oracle Autonomous AI Database** option is ideal for learning about Oracle Database and APEX. It comes with a minimum of 2 ECPU and 1 TB of storage and can be extended as needed. This service can also be used for production applications.

- The **APEX Application Development Service** is a flexible paid option that lets you focus on APEX development without worrying about database management. It provides 2 ECPU and 1 TB of storage and can be extended as needed.

### Types of Cloud Accounts

We offer two types of Cloud Accounts:

*Free Tier Accounts*: After you sign up for the free [Oracle Cloud promotion](https://signup.cloud.oracle.com/) or sign up for a paid account, you’ll get a welcome email. The email provides you with your cloud account details and sign-in credentials.

*Oracle Cloud Paid Accounts*: When your tenancy is provisioned, Oracle sends an email to the default administrator at your company with the sign-in credentials and URL. This administrator can create a user for each person who needs access to the Oracle Cloud. Check your email or contact your administrator for your credentials and account name.

### Objectives

- Learn how to log in to your Oracle Cloud account.

### Prerequisites

- Cloud account access is required but not mandatory.
- Cloud Account Name - The name of your tenancy (supplied by the administrator or in your Oracle Cloud welcome email).
- Username
- Password

Select one of the options below to proceed.

## Option 1: oracleapex.com

Signing up for oracleapex.com is simply a matter of providing details on the Workspace you wish to create and then waiting for the approval email.

1. Go to [oracleapex.com](https://www.oracle.com/apex/).

2. Select **Get Started**.

    ![Get started for free](images/get-started.png " ")

3. Under Getting Started with Oracle APEX, select **Sign Up for Free**.

    ![Request a free Workspace](images/request-workspace.png " ")

4. On the **Request a Workspace** page, enter your identification details – **First Name, Last Name, Email, Workspace name**.

    > **Note:** For Workspace, enter a unique name, such as first initial and last name.

    Select **Request Workspace**.

    ![Request a Workspace dialog](images/request-a-workspace.png " ")

    ![email from Oracle APEX](images/email-sent.png " ")

5. Check your email. You should get an email from Oracle APEX within a few minutes.

    > **Note:** If you do not get an email, go back to step 3 and make sure you entered your email correctly.

    In the email body, select **Create Workspace**.

    ![email from Oracle APEX](images/create-aoc-workspace.png " ")

6. Select **Continue to Sign In Screen**.

    ![Continue to Sign In Screen](images/continue-to-signin.png " ")

7. Enter your password, and select **Change Password**.

    ![Change password](images/enter-password.png " ")

8. You should now be in App Builder.

    ![App Builder home page](images/apex-builder.png " ")


## Option 2: Autonomous AI Database in Oracle Cloud

In this part, you will create an Oracle Cloud trial account. Once you have signed up for the service, you will create an *Autonomous AI* database. The final step in the process is to provision Oracle APEX.

1. Please [click this link to create your free account](https://signup.cloud.oracle.com). When you complete the registration process, you'll receive an account with a $300 credit and several "forever free" services that will enable you to complete the workshop for free. You can then use any remaining credit to continue to explore the Oracle Cloud. The forever free services will continue to work after the trial expires.

2. Soon after requesting your trial, you will receive a  **Get Started Now with Oracle Cloud** email.

   Make note of your **Username**, **Password**, and **Cloud Account Name**.

   ![Email with Username, Password, and Cloud Account Name](images/get-started-email.png " ")

3. Now that you have a service, you will log into your Oracle Cloud account, so that you can start working with various services.

    From any browser go to [https://cloud.oracle.com/en_US/sign-in](https://cloud.oracle.com/en_US/sign-in).

    Enter your **Cloud Account Name** in the input field and click the **Next** button. Select an identity provider and click **Next**.

   ![log in page for Oracle Cloud account](images/enter-oracle-cloud-account-name.png " ")

4. Enter your **User Name** and **Password** in the input fields, and click **Sign In**.

   ![log in page for Oracle Cloud account](images/enter-user-name-and-password.png " ")

5. From within your Oracle Cloud environment, you will create an instance of the Autonomous AI Database service.

    From the Cloud Dashboard, select the navigation menu icon in the upper left-hand corner, navigate to **Oracle AI Database** and then select **Autonomous AI Database**.

   ![Cloud Dashboard](images/database-atp.png " ")

6. Click **Create Autonomous AI Database**.

   ![Cloud Dashboard](images/click-create-autonomous-database.png " ")

7. Enter/ select the following:
    - Workload Type: **Transaction Processing** 
    - Always Free: Toggle **ON**
    - Choose database version: **26ai**
    - Admin Password: enter a **```SecretPassw0rd```** password for ADMIN 
    Click **Create**.

    ![Create Autonomous Database page](images/atp-settings-1.png " ")

    ![Create Autonomous Database page](images/atp-settings-2.png " ")

    ![Create Autonomous Database page](images/atp-settings-3.png " ")

8. You will be redirected to the Autonomous Database Details page for the new instance.

    Continue when the status changes from 'Provisioning' to 'Available':

    ![Autonomous Database Details page](images/status-provisioning.png " ")

    to

    ![Autonomous Database Details page](images/status-available.png " ")

9. Within your new database, APEX is not yet configured. Therefore, when you first access APEX, you will need to log in as an APEX Instance Administrator to create a workspace.

    Navigate to **Tool Configuration**. Under Oracle APEX, click **Copy** to copy the public access URL and open in a different tab.


    ![Launch APEX instance](images/launch-apex-inst.png " ")

    *Note: Always Free Autonomous Database will be stopped after being inactive for 7 days. If that happens, you need to click **More Actions** and then **Start** to start your Autonomous Database, and then **Open APEX**.*

10. Enter username as **Admin** and the Password for the Administration Services and click **Sign In**.

    The password is the same as the one entered for the ADMIN user when creating the ATP instance: **```SecretPassw0rd```**

    ![Administration Services login page](images/log-in-as-admin.png " ")

11. Select **Administration Services**.
    ![Select Administration Services option](images/select-admin-services.png " ")

12. Click **Create Workspace**.

    ![Create Workspace page](images/welcome-create-workspace.png " ")

13. Depending on how you would like to create your workspace, select **New Schema** or **Existing Schema**. If you are getting started, select **New Schema**.

    ![Choose type of schema](images/choose-schema.png " ")

14. In the Create Workspace dialog, enter the following:

      | Property | Value |
      | --- | --- |
      | Workspace Name | APEX_LL |
      | Workspace Username | GENDEV |
      | Workspace Password | **`SecretPassw0rd`** |

    Click **Create Workspace**.

    ![Create Workspace dialog](images/create-workspace.png " ")

15. In the APEX Instance Administration page, click the **APEX_LL** link in the success message.

    ![APEX Instance Administration page](images/log-out-from-admin.png " ")

16. Sign out from the **Administration Services** page.

    ![Sign out from Admin](images/log-out-from-admin1.png " ")

17. On the APEX log in page, enter **Username** and **``SecretPassw0rd``** for the password.

    ![APEX log in page](images/log-in-to-apex.png " ")

18. Once logged in, select the newly created Workspace name **APEX_LL**.

    ![APEX log in page](images/select-workspace.png " ")

    ![APEX Workspace](images/apex-workspace.png " ")

## Option 3: APEX Service

Oracle Application Development (APEX Service) is a low cost Oracle Cloud service offering convenient access to the Oracle APEX platform. Visit [https://apex.oracle.com/en/platform/apex-service/](https://apex.oracle.com/en/platform/apex-service/) to learn more about APEX service on Oracle Cloud.

In this part, you will create an Oracle APEX Application Development Service. Once you have signed up for the service, you will create an *APEX Service* instance. The final step in the process is to provision Oracle APEX workspace.

1. Please [click this link to create your free account](https://signup.cloud.oracle.com/). When you complete the registration process, you'll receive an account with a $300 credit that you can utilize to create an APEX Service. You can then use any remaining credit to continue to explore the Oracle Cloud.

2. Once the Sign up process is complete, you will be logged in automatically to the Oracle Cloud Infrastructure (OCI) Console.

    - In case you have closed the browser, you can always refer to the **Get Started Now with Oracle Cloud** email that you should have received to login to OCI Console.
    Make a note of your **Username**, **Password**, and **Cloud Account Name**.

    ![Oracle Cloud login page](images/get-started-email.png " ")

    - Alternatively, you can login to your Oracle Cloud account by accessing the following URL from your browser:
    [https://cloud.oracle.com](https://cloud.oracle.com).
    Enter your **Cloud Account Name** in the input field and click the **Next** button.

    ![Cloud login](images/enter-oracle-cloud-account-name.png " ")

    - Enter your **User Name** and **Password** in the input fields, and click **Sign In**.

    ![Cloud login](images/enter-user-name-and-password.png " ")

3. From the Cloud Dashboard, click on the hamburger menu on the upper-left corner. From the navigation menu, select **Developer Services** and then **APEX Application Development** or **APEX Instances**.

    ![APEX instance page](images/navigate-to-apex-service.png " ")

4. At the top of the APEX Instances page, click the **Create APEX Service**.

    ![APEX instance page](images/create-apex-service.png " ")

5. Select the **Always Free** option, enter **```SecretPassw0rd```** for the ADMIN password, then click **Create APEX service**.

    ![Create instance page](images/apex-service-settings-1.png " ")

    ![Create instance page](images/apex-service-settings-2.png " ")

    ![Create instance page](images/apex-service-settings-3.png " ")

6. The APEX Instances Details displays again.

   When the provisioning process completes, an orange 'Provisioning' badge changes to a green 'Available' badge. The Launch APEX button is enabled.

   ![Provisioning status](images/apex-logo-orange.png " ")

   ![Available status](images/apex-logo-green.png " ")

7. Before using a new APEX Service, you must set up your APEX Service instance by completing two tasks: create an initial APEX workspace and create an APEX user account.

   On the APEX Instance Details, click Launch APEX.

   ![APEX instance page](images/launch-apex.png " ")

8. The Oracle APEX Sign In page appears. 10. Enter username as **Admin** and the Password for the Administration Services and click **Sign In**.
The password is the same as the one entered for the ADMIN user when creating the APEX service: **```SecretPassw0rd```**

   ![APEX instance admin login page](images/log-in-as-admin.png " ")

9. Select **Administration Services**.
    ![Select Administration Services option](images/select-admin-services.png " ")

10. Click **Create Workspace**.

    ![Create Workspace page](images/welcome-create-workspace.png " ")

11. Depending on how you would like to create your workspace, select **New Schema** or **Existing Schema**. If you are getting started, select **New Schema**.

    ![Choose type of schema](images/choose-schema.png " ")

12. In the Create Workspace dialog, enter the following:

      | Property | Value |
      | --- | --- |
      | Workspace Name | APEX_LL |
      | Workspace Username | GENDEV |
      | Workspace Password | **`SecretPassw0rd`** |

    Click **Create Workspace**.

    ![Create Workspace dialog](images/create-workspace.png " ")

13. In the APEX Instance Administration page, click the **APEX_LL** link in the success message.

    ![APEX Instance Administration page](images/log-out-from-admin.png " ")

14. Sign out from the **Administration Services** page.

    ![Sign out from Admin](images/log-out-from-admin1.png " ")

15. On the APEX log in page, enter **Username** and **``SecretPassw0rd``** for the password.

    ![APEX log in page](images/log-in-to-apex.png " ")

16. Once logged in, select the newly created Workspace name **APEX_LL**.

    ![APEX log in page](images/select-workspace.png " ")

    ![APEX Workspace](images/apex-workspace.png " ")

## Summary

At this point, you know how to create an APEX Workspace and you are ready to start building amazing apps, fast.

You may now proceed to the next lab.

## Acknowledgements

- **Author** -  Ankita Beri, Senior Product Manager
- **Last Updated By/Date**: Ankita Beri, Senior Product Manager, June 2026
