# Lab 3: Build the Interview Schedule as an Interactive Grid

## Introduction

An interview schedule changes quickly, and recruiters should not have to leave the page to keep it accurate. In this lab, you will build an editable grid that puts each interview stage and its working details in one place.

Estimated Time: 10 minutes

### Objectives

In this lab, you will:

- Create an Interactive Grid from the `TMS_INTERVIEW_STAGES` table.
- Keep candidate and requisition identifiers visible but protected from edits.
- Hide audit fields and save a change from the grid.

## Task 1: Add the Interactive Grid

1. In Talent Acquisition Portal Application, open **Interview Schedule** page.

    ![Interview Schedule grid source](images/interview-schedule-grid-source.png "")

2. In the Rendering tree (left pane), right click on Body and click **Create Region**.

    ![Add a new Region](images/click-create-region.png "")

3. In the Property Editor, enter/select the following properties:
    - Under Identification:
        - Name: **Interview Stages**
        - Type: **Interactive Grid**
    - Under Source:
        - Table Owner: **Parsing Schema**
        - Table Name: `TMS_INTERVIEW_STAGES`

    ![Set Interactive Grid Properties](images/set-interactive-grid-properties.png "")

4. In the Property Editor, Click **Attributes** Tab and then:
    - Under Edit > Enabled: Yes

    ![Enable Edit option](images/enable-edit.png "")

## Task 2: Configure editable columns

1. In the left pane, expand the report columns of the Interactive Grid Region.

    ![Expand the report columns](images/expand-report-columns.png)

2. Select the column **CANDIDATE\_ID**.

    ![Select the Candidate ID column](images/select-candidate-id-column.png)

3. In the right pane:
    - Under Identification > Type: Display Only

    ![Set Candidate ID  as Display only](images/update-candidate-id-type.png)

4. Similarly, Update the Identification **Type** for **REQ\_ID** and **STAGE\_NAME** as Display Only.

  |Column Name | Identification Type |
  |----------|-------|
  | REQ\_ID | Display Only |
  | STAGE\_NAME | Display Only |

    ![Set REQ ID as Display only](images/update-req-id-type.png)

    ![Set Stage Name as  Display only](images/update-stage-name-type.png)

5. Next, you will need to hide all the Audit Columns **CREATED\_BY**, **CREATED\_AT**, **UPDATED\_BY**, and **UPDATED\_AT**. To do this, you can set the Type of the column to Hidden, which will not display the column on the frontend.

    - To select these four Columns, click on the **CREATED\_BY** column under the Interview Stages region, and then hold shift and click on the last column, **UPDATED_AT**.

6. Then, In the **Property Editor**, Update the Identification **Type** as **Hidden**.

    ![Set Audit Columns type as Hidden](images/update-audit-columns-type.png)

7. Save and Run the Page.

    ![Save and Run Page](images/save-and-run-page.png)

8. Navigate through the **Interview Schedule** Grid page.

    ![Interview Schedule page](images/check-interview-schedule-page.png.png "")

9. Change an editable cell, select **Save**, and confirm that the update is committed.

    ![Interview Schedule inline edit](images/interview-schedule-inline-edit.png "")

    ![Interview Schedule save Edit](images/interview-schedule-save-edit.png "")

## Summary

You created an editable Interview Schedule grid with the right balance of visibility and control. Recruiters can see the interview context, keep audit data out of the way, and save schedule changes directly in the grid.

## Acknowledgements

* **Author** - Roopesh Thokala, Principal product manager
* **Last Updated By/Date** - Roopesh Thokala, July 29, 2026
