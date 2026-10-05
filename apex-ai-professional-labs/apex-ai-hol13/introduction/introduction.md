# Forms Development

## Introduction

The Talent Acquisition Portal (TAP) and Employee Self Service (ESS) applications already contain individual form pages. In this module, you will complete these forms so recruiters can review candidate information, record interview feedback, and update candidate stages. Employees will be able to update their contact details and upload a profile photo or a supporting document for a leave request.

Estimated Workshop Time: 25 minutes

*Note: The four lab estimates are 10, 5, 5, and 5 minutes. Allow additional time if you need to prepare the starter applications or replace the asset placeholders.*

### Objectives

In this workshop, you will:

- Organize Candidate Profile into two columns and add photo display, CV upload, and CV download.
- Link Candidate Profile to Interview Feedback using a master-detail relationship.
- Create an editable interactive grid for bulk candidate stage updates.
- Extend My Profile and Leave Request pages in ESS Application with contact details and file uploads.

### Prerequisites

- An Oracle APEX **26.1** workspace with the TAP and ESS applications from the earlier modules.
- The TMS schema and sample data, including candidates, interview stages, employees, jobs, departments, and leave requests.
- TAP **Page 11: Candidate Profile** and **Page 13: Interview Feedback**, with the feedback page configured as a modal dialog.
- ESS **Page 4: My Profile** and **Page 5: Leave Request**.
- An employee test account whose login matches exactly one email address in **TMS_EMPLOYEES**, ignoring letter case.

*Note: These instructions use the page numbers from the workshop applications. If your page numbers differ, replace the page numbers and item prefixes throughout the tasks. Property labels can vary with your Oracle APEX version; use the Property Editor help for the equivalent setting.*


## Labs

| Lab | Application | Estimated Time |
| --- | --- | --- |
| [Complete the Candidate Profile Form](../lab-1-complete-candidate-profile-form/lab-1-complete-candidate-profile-form.md) | TAP | 10 minutes |
| [Link Candidate Profile and Interview Feedback](../lab-2-candidate-profile-as-master-detail/lab-2-candidate-profile-as-master-detail.md) | TAP | 5 minutes |
| [Build a Bulk Stage Update Interactive Grid](../lab-3-build-bulk-stage-update-ig/lab-3-build-bulk-stage-update-ig.md) | TAP | 5 minutes |
| [Extend ESS My Profile and Leave Request](../lab-4-ess-my-profile-form/lab-4-ess-my-profile-form.md) | ESS | 5 minutes |

## Downloads

The candidate photo script is included in Lab 1. The ESS sample update script, sample photo, and PDF files have labeled placeholders. Follow the download notes in each lab and the [asset checklist](../ASSET-CHECKLIST.md).


## What Carries Forward

Module 14 organizes navigation across TAP and ESS. Keep the pages and item names created here available for that work. Module 18 adds recruiter authorization to Bulk Stage Update; creating a navigation entry alone does not restrict access.

## Acknowledgements

- **Author** - Roopesh Thokala, Principal Product Manager
- **Last Updated By/Date** - September 2026
