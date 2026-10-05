# Build a Bulk Stage Update Interactive Grid

## Introduction

Recruiters may need to move several candidates to a new stage at the same time. In this lab, you will create a Bulk Stage Update page that lets recruiters update the current stage for multiple candidates.

Estimated Lab Time: 5 minutes

### Objectives

In this lab, you will:

- Create an editable Interactive Grid for candidates who are not hired or rejected.
- Make **CURRENT\_STAGE** the only editable column and use valid candidate-stage values.
- Add the page to navigation and prepare it for recruiter authorization in Module 18.

## Task 1: Create the Editable Interactive Grid Page

Create the page and its Interactive Grid together in the Create Page wizard.

1. Click **App Builder** and open **Talent Acquisition Portal**.

    ![Select Talent Acquisition Portal in App Builder](images/screenshot-select-talent-acquisition-portal.png " ")

2. Click **Create Page**.

    ![Click Create Page in the application home page](images/screenshot-create-page.png " ")

3. Under **Component**, select **Interactive Grid**.

    ![Select Interactive Grid as the page component](images/screenshot-select-interactive-grid.png " ")

4. Under **Page Definition**, enter **Bulk Stage Update** as the page name. Leave **Page Mode** set to **Normal** and **Include Form Page** disabled. Under **Data Source**, select **Local Database**.

    ![Set the page name and select Local Database as the data source](images/screenshot-page-definition.png " ")

    The wizard initially selects **Table** as the source type. Change it to **SQL Query** in the next step.

5. Under **Source Type**, select **SQL Query** and enter the following query. Make sure **Editing Enabled** is set to **Yes**.

    ```sql
    <copy>
    SELECT
        c.candidate_id,
        c.first_name || ' ' || c.last_name AS candidate_name,
        c.current_stage,
        c.applied_date,
        c.req_id
    FROM tms_candidates c
    WHERE c.current_stage NOT IN ('Hired', 'Rejected')
    </copy>
    ```

    ![Enter the SQL query and enable Interactive Grid editing](images/screenshot-enter-grid-query.png " ")

6. Expand **Navigation** and enable **Use Navigation** to add the page to the application menu. Click **Next**.

7. Under **Primary Key**, select **CANDIDATE\_ID** for **Primary Key Column 1**. Leave **Primary Key Column 2** unselected, then click **Create Page**.

    ![Set CANDIDATE\_ID as the Interactive Grid primary key and create the page](images/screenshot-select-candidate-id-primary-key.png " ")

## Task 2: Configure the Grid for Stage Updates

In this task, you will configure **CURRENT\_STAGE** as the only editable column.

1. In the Rendering tree, select the **Bulk Stage Update** Interactive Grid region.

2. In the Property Editor, select the **Attributes** tab and set the following properties:
    - Under **Edit > Enabled**, select **Yes**.
    - Under **Allowed Operations**:
        - **Add Row**: Off
        - **Update Row**: On
        - **Delete Row**: Off

    ![Enable updates and disable add and delete operations](images/screenshot-enable-grid-updates-only.png " ")

3. In the Rendering tree, expand the **Columns** node and select **CANDIDATE\_ID**. In the Property Editor, set **Identification > Type** to **Display Only**.

    ![Set CANDIDATE\_ID to Display Only](images/screenshot-set-candidate-id-display-only.png " ")

4. Similarly, set the **Identification > Type** of the following columns to **Display Only**:

    | Column Name | Identification > Type | Source > Query Only |
    | --- | --- | --- |
    | CANDIDATE\_NAME | Display Only | Yes |
    | APPLIED\_DATE | Display Only | Yes |
    | REQ\_ID | Display Only | Yes |

    ![Set the candidate name, applied date, and requisition ID to Display Only](images/screenshot-set-read-only-columns.png " ")

5. Select the **CURRENT\_STAGE** column. In the Property Editor, set:
    - Under **Identification > Type**, select **Select List**.
    - Under **List of Values > Type**, select **Static Values**.

    ![Configure CURRENT\_STAGE as a Select List with Static Values](images/screenshot-configure-current-stage-select-list.png " ")

    Enter the following values. Use the same text for each display value and return value:

    | Display Value | Return Value |
    | --- | --- |
    | Applied | Applied |
    | Screening | Screening |
    | Interview | Interview |
    | Offer | Offer |
    | Hired | Hired |
    | Rejected | Rejected |

    These are the values allowed by the `TMS_CANDIDATES.CURRENT_STAGE` constraint. Include **Hired** and **Rejected** so a recruiter can move an active candidate into either final stage. Do not use **TMS\_INTERVIEW.STAGES** here; that shared LOV is used for interview `STAGE_NAME` values, which differ from candidate `CURRENT_STAGE` values.

    ![Enter the six allowed candidate stage values](images/screenshot-enter-candidate-stage-values.png " ")

6. Click **Save**.

    ![Save the Interactive Grid configuration](images/screenshot-save-grid-settings.png " ")

## Task 3: Run and Check the Grid

1. Click **Save and Run Page**.

    ![Save and run the Bulk Stage Update page](images/screenshot-save-and-run-page.png " ")

2. Confirm the grid shows candidates whose current stage is not **Hired** or **Rejected**.

    ![Review the Bulk Stage Update grid at runtime](images/screenshot-bulk-stage-update-runtime.png " ")

3. Change a candidate's **CURRENT\_STAGE** and select a new stage from the list.

    ![Select a new candidate stage in the grid](images/screenshot-select-candidate-stage.png " ")

4. Click the grid toolbar's **Save** and confirm that the change is saved.

    ![Confirm that the candidate stage update was saved](images/screenshot-confirm-stage-update-saved.png " ")

   If you set the stage to **Hired** or **Rejected**, the candidate disappears from this grid after saving because the query filters out those stages.

## Summary

You created an editable Bulk Stage Update Interactive Grid, marked **CANDIDATE\_ID** as its primary key, and limited editing to **CURRENT\_STAGE** with values allowed by the candidate table. The grid's toolbar Save button saves the changes. Module 18 adds recruiter-only authorization.

You may now proceed to the next lab.

## Acknowledgements

- **Author** - Roopesh Thokala, Principal Product Manager
- **Last Updated By/Date** - September 2026
