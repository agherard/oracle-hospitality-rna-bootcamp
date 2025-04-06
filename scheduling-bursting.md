# Scheduling and Bursting Reports

Getting started with Oracle Hospitality Reporting and Analytics

1. [Accessing the Reporting Application](#1-accessing-the-reporting-application) 
2. [Scheduling an Analysis Report](#2-scheduling-an-analysis-report)
3. [Job Scheduler and Bursting BI Publisher Reports](#3-job-scheduler-and-bursting-bi-publisher-reports)

## 1. Accessing the Reporting Application

1. Access the R&A Portal application from your instance or the provided instance.
2. b.	From the Portal home page, select on the Reports and Dashboards Tile, alternatively from the drop down menu you can select Reports and Dashboards.

![alt text](images/rna-portal.png "R&A Portal Landing Page")

## 2. Scheduling an Analysis Report

1. Scheduling an analysis report for delivery can be achieved by utilizing the Agents functionality in R&A.  There are multiple ways to schedule an agent.  In this first activity, we will deliver an Analysis with a condition to your users email address

2.	Access the Catalog by choosing the catalog menu from the top left corner of the OAS banner

![alt text](images/select-catalog-scheduling.png "Access the Catalog")

3.	Access the Shared Folders/ Htl Templates directory

![alt text](images/access-shared-folder-htl-templates.png "Access Shared Folder/Htl Templates directory")

4.	Select the Managers Overview Report, and select the More dropdown menu

![alt text](images/select-folder-managers-overview-report.png "Access the Managers Overview Report")

5.	Select the Schedule option from the dropdown menu

![alt text](images/select-schedule-option-dropdown.png "Select Schedule Option from Dropdown menu")

6.	On the General Tab, leave the Priority as Normal and set the Run As option to Recipient

![alt text](images/scheduling-config-general-tab.png "Set Priority of Scheduling in General Tab")

7.	Move to the Schedule Tab and make below updates to the scheduler
* Frequency = Once
* Start = todays date, and 15 minutes from current time making sure the time zone is set correctly

![alt text](images/set-scheduling-frequency.png "Set Scheduling Frequency")

8.	Move to the condition tab. Here we are just reviewing the information on the screen to ensure there is a condition, and we will test the condition to see if it is true, by selecting the Test option next to the condition

![alt text](images/scheduling-condition-tab.png "Set Scheduling Conditions")

* The condition will either come back as True or False

![alt text](images/scheduling-condition-result.png "The Condition will either return true or false")

9.	Move to the Delivery Content Tab.  When scheduling from an existing Analysis, the content will automatically be selected

![alt text](images/delivery-content-tab-scheduling.png "Select Delivery Content Tab")

* Fill in the Subject with the title of the e-mail you want

![alt text](images/fill-delivery-content-scheduling.png "Fill in the Subject with the title of the e-mail")

* Select the format dropdown menu, and choose PDF as the file format

![alt text](images/select-pdf-format-scheduling-delivery.png "Set format delivery as PDF file format")

* When changing the format, the Delivery option will automatically change to Deliver as attachment.  Add a text to the Attachment note, which will be in the body of the email

![alt text](images/add-note-attachment-note-scheduling.png "Define Attachment Note")

* Select the If Condition is False check box and add a note to deliver if the condition returns False

![alt text](images/add-note-condition-false-scheduling.png "Set note if condition is false")

* Move to the recipients Tab to verify that your User is shown in the recipients box and other options match the screenshot

![alt text](images/confirm-recipients-scheduling.png "Confirm recipient of report delivery")

* Move to the Destinations Tab, and validate that Home Page and Dashboard as well as Devices active Delivery Profile are selected

![alt text](images/destination-tab-scheduling.png "Confirm destination tab option for report scheduling")

* Select the Save (disk) icon from the top left menu

![alt text](images/save-scheduling.png "Save Scheduling configuration done")

* Select Shared folder, and using the add Folder icon, create a folder call Agents

![alt text](images/create-folder-agents-scheduling.png "Create folder Agents in Shared Folders")

* Name the Agent, Manager Overview Agent and select OK

![alt text](images/name-agent-scheduling.png "Name the Agent, Manager Overview Agent")

* After the agent is saved, you should see the robot icon is not greyed out, meaning that it is active. The Agent should deliver based on the scheduled time setup

![alt text](images/agent-is-active-scheduling.png "Confirm Agent is active")

## 3. Job Scheduler and Bursting BI Publisher Reports

1.	Scheduling a BI Publisher report for delivery can be achieved by utilizing the Job Scheduler functionality in R&A. There are multiple ways to schedule these jobs. In this first activity, we will deliver a BI Publisher report with bursting to your email address.

2.	Access the Catalog by choosing the catalog menu from the top left corner of the OAS banner

![alt text](images/select-catalog-scheduling.png "Access the Catalog")
 
3.	Access the Shared Folders/ {Org Code}/Bootcamp/{YOUR NAME} directory

![alt text](images/access-shared-folder-bip.png "Access Shared Folders with Data Model")

4.	Edit the Data Model by selecting the Edit Option on the Stats Matrix data model created in the Convert analysis to BI Publisher report Lab

![alt text](images/edit-data-model-bip-report.png "Edit Data Model")
  
5.	Select on the Bursting option and select the + icon to add a new bursting query

![alt text](images/select-bursting-option-bip.png "Select Bursting Option")
 
6.	Rename the bursting  from Bursting 1 to EMAIL
 
![alt text](images/rename-bursting-email.png "Rename Bursting from 1 to EMAIL")

7.	In the bottom section of the bursting query, change the Split By and Deliver By values to be /DATA_DS/G_1/PROPERTY using the dropdown menu

![alt text](images/select-slip-delivery-bursting.png "Define Split By and Delivery By options of bursting")
 
8.	Copy the below SQL query into the SQL Query window.  In the next step we will update the parameters to match what is required. 

```
select DISTINCT
RESORT KEY,
'TEMPLATE_NAME' TEMPLATE,
'RTF' TEMPLATE_FORMAT,
'en-US' LOCALE,
'PDF' OUTPUT_FORMAT,
'Email' DEL_CHANNEL, -- Can be any of the output type part of the Template
'File_name_formula - '||Resort||'_'||to_Char(Sysdate-1,'YYYYMMDD') OUTPUT_NAME,
'xxx.xxx@xxx.com' PARAMETER1, -- TO ADDRESS
'yyy.yyy@yyy.com' PARAMETER2, -- CC ADDRESS
'noreply_cds_gbu-analytics@gbua.ocs.oraclecloud.com' PARAMETER3, -- FROM ADDRESS
'EMAIL_SUBJECT' PARAMETER4,
'EMAIL_BODY' PARAMETER5,
'true' PARAMETER6
from RESORT
```

9.	Update the following rows in the query to correct the parameters to meet your specific job

* TEMPLATE – The report name that will be used for bursting. The report name can be retrieved from the Properties menu of the report.
* OUTPUT_FORMAT – The output format of the delivered report such as PDF.
* Replace with: 'Statistics_Matrix_'||RESORT||'.pdf'
* TO ADDRESS – The Email address/es to which the report will be sent. To enter multiple email addresses, use the following format: ‘xxx@xxxx.com,yyy@yyyy.com’
* PARAMETER 4 – Indicates the subject line of the email.
* PARAMETER 5 – Indicates the email body.
* Replace with: 'Attached is the output for '||RESORT ||'.pdf' 
 
![alt text](images/bursting-sql-query.png "Set Bursting SQL Query")

10. Save the data model by selecting on the DISK icon

![alt text](images/save-data-model-bursting.png "Save the Data Model")

11. Select the Catalog option in the top right corner.  You should be brought directly into the latest catalog location, but if not navigate back to Shared Folders/ {Org Code}/Bootcamp/{YOUR NAME} directory
 
 ![alt text](images/select-catalog-data-model-bursting.png "Go Back to the Catalog")

12. Edit the Stats Matrix Report file
 
 ![alt text](images/edit-stats-matrix-report.png "Edit the Stats Matrix Report file")

13. Select the Properties option in the top right corner

![alt text](images/select-options-stats-matrix-report.png "Select the Properties option")

14. Check the Enable Bursting option, and ensure the Email option is selected in the drop down.  Then select OK

![alt text](images/enable-bursting-option.png "Enable Bursting Option")
 
15. Select the disk Icon to save the report
 
 ![alt text](images/save-bursting-properties.png "Save the Report with the Bursting definitions set")

16. Select the Catalog option in the top right corner.  You should be brought directly into the latest catalog location, but if not navigate back to Shared Folders/ {Org Code}/Bootcamp/{YOUR NAME} directory
 
![alt text](images/select-catalog-data-model-bursting.png "Go Back to the Catalog")

17. Select the more options dropdown on the Stats Matrix Report and select Schedule

![alt text](images/schedule-stats-matrix-report.png "Schedule Stats Matrix Report")

18. On the General tab, you can select a resort or leave it as all

![alt text](images/scheduling-bip-report-general-tab.png "Confirm options in General tab of BIP report scheduling")
 
19. Move to the output tab, and ensure that Use Bursting Definition to Determine Output & Delivery Destination, Make Output Public and Save Data for Republishing are all checked

![alt text](images/scheduling-bip-report-output-tab.png "Set options in Output tab of BIP report scheduling")
 
20. Move to the Schedule Tab, and validate that Frequency = Once, and Run Now is selected

![alt text](images/scheduling-bip-report-schedule-tab.png "Set options in Schedule tab of BIP report scheduling") 

21. Select the Submit option in the top right corner, to send the Report.  

![alt text](images/submit-bip-report-scheduling.png "Submit BIP Report Scheduling")  

22. Name the report job Stats Matrix Test and select OK.  You will get a notification that the report job was submitted successfully
 
![alt text](images/name-report-job-stats-matrix-bip.png "Name the report job Stats Matrix Test")
