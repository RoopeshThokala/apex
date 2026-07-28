# Lab 4: Create Job Openings Cards Page

## Introduction

When a hiring manager asks what roles are open, the answer should be easy to browse. In this lab, you will turn open requisitions into a clean job board where each card shows the essentials and Smart Filters help the recruitment team find the right openings quickly.

Estimated Time: 5 minutes

### Objectives

In this lab, you will:

- Create a Cards page from open job requisitions.
- Present each opening with department, headcount, opening date, and an icon.
- Add department and headcount filters to narrow the job board.

## Task 1: Create the Job Openings page

1. In the Talent Acquisition Portal application, click **Create Page**.

    ![Create a page](images/create-job-openings-page.png "")

2. In Create a Page wizard, select **Cards** as the page type and click **Next**.

    ![Select Cards as Page Type](images/select-cards-page.png "")

3. Enter **Job Openings** as the page name, then click **Create Page**.

    ![Name the Job Openings page](images/name-job-openings-page.png "")

4. In **Create Cards** page:
    - Under Page Definition > Name: **Job Openings**.
    - Under Data Source:
        - Data Source: **Local Database**
        - Source Type: **SQL Query**
        - Enter a SQL SELECT statement: **Enter the following query**
            <copy>
            ```sql
                SELECT
                    R.REQ_ID,
                    J.TITLE,
                    D.NAME AS DEPT,
                    R.HEADCOUNT AS HEADCOUNT,
                    TO_CHAR(R.OPEN_DATE, 'DD-Mon-YYYY') AS OPEN_DATE
                FROM
                    TMS_JOB_REQUISITIONS R
                    JOIN TMS_JOBS J
                        ON R.JOB_ID = J.JOB_ID
                    JOIN TMS_DEPARTMENTS D
                        ON R.DEPT_ID = D.DEPT_ID
                WHERE
                    R.STATUS = 'Open'
            ```
            </copy>

        - Click **Next**

    ![Enter Job Openings Page Definitions](images/cofigure-cards-page.png "")

5. In the **Create Cards** wizard, under **Cards Attributes**, set **Title Column** to **TITLE**. Then, click **Create Page**.

    ![Set the card title column](images/set-card-title-column.png "")

## Task 2: Configure the Cards region

1. Under Page Rendering, Select **Job Openings** region.

    ![Set Cards Region](images/select-job-openings.png "")

2. With the **Job Openings** Cards region selected, in the Property Editor, Under **Region**, set **Order By Type** to **None**.

    ![Set Cards order by type](images/set-cards-order-by.png "")

3. In Property Editor, select **Attibutes**. Under **Card**, enter or select the following properties:

    - Under Subtitle > Column: **Department**
    - Under Body: 
        - Advanced Formatting: **Yes**
        - HTML Expression:
            <copy>
            ```html
            <strong>Headcount:</strong> &HEADCOUNT.
            <br>
            <strong>Open since:</strong> &OPEN_DATE.
            ```
            </copy>
    - Under **Icon and Badge**:
        - Icon Source: **Icon Class**
        - Icon CSS Classed: `fa-briefcase`

    ![Configure Job Openings card attributes](images/configure-job-openings-card.png "")

4. Now, In the Rendering Tree(Left Pane), Right click on P13\_ORDER\_BY under Sort Order, if exists, and click **Delete**.

    ![Delete Sort Order](images/delete-sort-order.png "")

## Task 3: Add Smart Filters

1. In the Rendering tree, right-click **Body** and select **Create Region**.

    ![Create Smart Filters region](images/create-job-openings-smart-filters.png "")

2. Drag and drop the **New** region above **Job Openings** region to re-order the sequence.

    ![Move Smart filters Region](images/move-smart-filters.png "")

3. Select the Newly created region **New**. Then, in the Property Editor, enter or select the following properties:

    - Under Identification:
        - Name: **Smart Filters**
        - Type: **Smart Filters**
    - Under Source:
        - Filtered Region: **Job Openings**

    ![Configure Smart Filters region](images/configure-job-openings-smart-filters.png "")

4. In the Rendering tree, expand **Smart Filters** and right click on **Filters**. Click **Create Filter**.

    ![Add Department Filter](images/add-department-filter.png "")

5. In Property Editor, enter or select the following properties:
    - Under Identification
        - Name: **P13\_DEPARTMENT**
        - Type: **Checkbox Group**
    - Under List of Values > Type: **Distinct Values**
    - Under Source:
        - Database Column: **DEPARTMENT**
        - Data Type: **VARCHAR2**

    ![Configure Department Filter](images/configure-department-filter.png "")

6. Similarly, create another filer in the **Rendering Tree**. Then, in Property Editor, enter or select the following properties:

    - Under Identification
        - Name: **P13\_HEADCOUNT**
        - Type: **Range**
    - Under Label > Label: **Headcount Range**
    - Under List of Values > Type: **-Select-**
    - Under Source:
        - Database Column: **HEADCOUNT**
        - Data Type: **NUMBER**

    ![Configure Headcount Range Filter](images/configure-headcount-filter.png "")

7. Save and run the page.

    ![Run Job Openings page](images/run-job-openings-page.png "")

    ![Ran Job Openings page](images/job-openings-page.png "")

8. Verify that the Cards page shows open jobs and that both filters narrow the results.

    ![Verify Job Openings page](images/verify-job-openings-page.png "")

8. Apply **Department** Filters and check the narrowed Results.

    ![Apply Department Filters](images/apply-department-filters.png "")

## Summary

You created a browsable Job Openings page that shows the details recruiters need at a glance. With department and headcount filters in place, the team can move from a broad list of roles to the openings that matter most.

## Acknowledgements

* **Author** - Roopesh Thokala, Principal product manager
* **Last Updated By/Date** - Roopesh Thokala, July 29, 2026
