# Convert Analysis Report to a BI Publisher Report

Getting started with Oracle Hospitality Reporting and Analytics

1. [Accessing Reports](#1-accessing-catalog)
2. [Converting an Analysis Report to a BIP Publisher Report](#2-converting-an-analysis-report-to-a-bi-publisher-report)

## 1. Accessing Catalog

1. Access the R&A Portal application from your instance or the provided instance.
2. From the Portal home page, select on the Reports and Dashboards Tile, alternatively from the drop down menu you can select Reports and Dashboards.

![alt text](images/rna-portal.png "R&A Portal Landing Page")

3. From the main Oracle Analytics page, select the Catalog option

![alt text](images/access-catalog.png "Accessing the Catalog")

## 2. Converting an Analysis Report to a BI Publisher Report

1. Open the Shared Folders > Htl Templates folder and select the Statistics Matrix analysis report

![alt text](images/statistics-matrix-htl-templates.png "Statistics Matrix Analysis Report")

2. Select the More > Copy option under the report or use the Copy option on the toolbar

![alt text](images/copy-analysis-report.png "Copy Statistics Matrix Analysis Report")

3. Open the Shared Folder/{OrgCode}/Bootcamp/YOURNAME folder

4.	Use the Paste option on the Toolbar to paste a copy of the Statistics Matrix in your Bootcamp folder

![alt text](images/paste-analysis-report.png "Paste Statistics Matrix Analysis Report")

5.	Click Edit on the Statistics Matrix report and access the Criteria tab

![alt text](images/criteria-tab-stats-matrix-report.png "Access Criteria Tab on Statistics Matrix Report")

6.	Delete Location Filter by moving the mouse over the filter and clicking the X

![alt text](images/delete-location-filter.png "Delete Location Filter")

7.	Mouse over Settings and click Filter to add a Property Filter 

![alt text](images/stats-report-add-property-filter.png "Add Property Filter")

8.	In the Value field, choose a single property and click OK

![alt text](images/stats-report-select-property.png "Select Property for filter")

9.	Edit the Business Date Filter by moving the mouse over the filter and clicking the pencil icon

![alt text](images/edit-business-date-stats-report.png "Select Business Date")

10. Change the Operator from is Prompted to Is Between and choose two previous business dates

![alt text](images/change-operator-stats-report.png "Change Business Date Operator on the Report")

11. Click the Save icon to Save the Report

12. Click on Create > Data Model

![alt text](images/create-data-model.png "Create Data Model")

13. Under the Diagram tab, click the Plus icon and select Analysis

![alt text](images/data-model-select-analysis.png "Select Analysis Diagram for Data Model")

14. Set the name of the Data Model to Stats Matrix

![alt text](images/select-name-data-model.png "Define name to save the Data Model")

15. Click the magnifying glass icon and select the Statistics Matrix copy you created under the Shared Folder/{OrgCode}/Bootcamp/YOURNAME folder

16. Set the Time Out value to 90 and click OK

17. Open the Structure tab and add an Alias to all fields. As these are XML Tags, no spaces or special characters are allowed. Suggest use of underscore

![alt text](images/structure-data-sets-data-model.png "Add Alias to fields in Structure of Data Model")

18. Select the Data tab and click the View button

![alt text](images/view-data-from-data-model.png "View Data of Data Model")

19. Click the Save As Sample Data button

![alt text](images/save-as-sample-data-dm.png "Save as Sample Data for Data Model")

20. Click the Save icon to save the Data Model

21. Name the Data Model “Stats Matrix” and save under the Shared Folder/{OrgCode}/Bootcamp/YOURNAME folder

![alt text](images/save-new-data-model.png "Save new Data Model in Shared Folders")

22. Click on Create and select the Report option

![alt text](images/select-create-report-option.png "Create new Report")

23. At Create Report prompt, press Cancel and click OK to cancel report creation

![alt text](images/use-data-model-create-report.png "Select Data Model to Create new Report")

24. Click the magnifying glass icon and select the Stats Matrix Data Model you created under the Shared Folder/{OrgCode}/Bootcamp/YOURNAME folder

![alt text](images/save-new-dm-report-into-shared-folder.png "Save new Data Model Report in Shared Folder")

25. Click the OK button to load the Data Model

26. Click on the Generate option

![alt text](images/generate-rtf-layout-dm.png "Generate RTF Layout based on Selected Data Model")

27. Under Template Name, call this Stats Matrix and click Generate

![alt text](images/generate-layout-dm.png "Auto Generate Layout")

28. Select the View a List option

![alt text](images/view-list-layout-dm.png "View a List")

29. Under Output Formats select the drop down list and enable the Data (CSV) option

![alt text](images/select-csv-output-dm.png "Select CSV output for Data Model")

30. Change the Default Format to Data (CSV)

31. Click View Thumbnails

![alt text](images/view-thumbnails-dm.png "View Thumbnail of Data Modell")

32. Click the Save icon and save the report as “Stats Matrix Report” under the Shared Folder/{OrgCode}/Bootcamp/YOURNAME folder

![alt text](images/save-stats-report-as-dm-shared-folder.png "View Thumbnail of Data Model")

33. Click the Properties button

![alt text](images/view-dm-properties.png "View Properties of Data Model")

34. Uncheck the Auto Run option and click OK to save

![alt text](images/uncheck-auto-run-option-dm.png "Uncheck Auto Run Option from Data Model")

35. Click the View Report button

36. Click the Apply button
