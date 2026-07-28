# Lab 2: Add AI Interactive Report to Job Requisitions

## Introduction

Recruiters often start with a question, not a set of filters. In this lab, you will make the Job Requisitions report understand the language of the hiring team, so a plain-English request can become a useful report filter.

Estimated Time: 5 minutes

### Objectives

In this lab, you will:

- Enable AI Interactive Report on Job Requisitions.
- Give the department and status columns clear business context.
- Test a recruiter-style natural-language request.

## Task 1: Enable AI Interactive Report

1. From the **Candidate Pipeline** page, click on the **Page Finder** and select **Job Requisitions** Page.

    ![Select Job Requisitions Page](images/select-job-requistions-page.png "")

2. Click on the **Job Requisitions** region.

    ![Click Job Requisitions Region](images/click-job-requisitions.png "")

3. Then in the Property Editor, select **Attributes** Tab and then:

    - Under Generative AI > Enable **AI Interactive Report**.

    ![Enable AI Interactive Report](images/enable-ai-interactive-report.png "")

## Task 2: Add column context

Column context helps the AI interpret business terms in a prompt.

1. In the left pane, expand the report columns.

    ![Expand the report columns](images/expand-report-columns.png)

2. Select the column **DEPT\_ID**.

    ![Select the DEPT ID column](images/select-dept-id-column.png)

3. In the right pane, scroll to the **Generative AI** section for the selected column. If the section is collapsed, expand it.

    ![Open the Generative AI section](images/open-generative-ai-section-for-qty-to-target.png)

4. In **Column Context**, enter the following context value:

    ```
    <copy>
    Organizational department name (e.g., Sales, Engineering, HR)
    </copy>
    ```

    ![Enter the DEPT_ID column context](images/enter-dept-id-column-context.png)

5. Select the second column **STATUS**.

    ![Select the Status column](images/select-status-column.png)

6. In the **Generative AI** section, enter the following **Column Context** value:

    ```
    <copy>
    Requisition status; values include Open, Filled, Pending Approval, Draft
    </copy>
    ```

    ![Enter the PRIORITY_CODE column context](images/enter-status-column-context.png)

## Task 3: Test a natural-language filter

1. Save and run the page.

    ![Save and Run the page](images/save-and-run-page.png)

2. In the natural-language filter bar, enter `Show me Engineering requisitions open for more than 30 days`.

    ![Search using Natural language filter](images/job-requisitions-natural-language-filter.png "")

    ![Search using Natural language filter chat](images/job-requisitions-natural-language-filter-1.png "")

3. Confirm that APEX converts the prompt to a filter and shows matching requisitions.

    ![Job Requisitions natural-language filter result](images/job-requisitions-filter-result.png "")

    ![Job Requisitions natural-language filter result](images/job-requisitions-filter-result-1.png "")


## Summary

You enabled AI Interactive Report and explained the meaning of the department and status fields. Recruiters can now start with a natural-language question and quickly focus the requisitions report.

## Acknowledgements

* **Author** - Roopesh Thokala, Principal product manager
* **Last Updated By/Date** - Roopesh Thokala, July 29, 2026
