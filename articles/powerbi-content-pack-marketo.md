<properties pageTitle="Marketo content pack for Power BI" description="Marketo content pack for Power BI" services="powerbi" documentationCenter="" authors="v-anpasi" manager="mblythe" editor=""/>
<tags ms.service="powerbi" ms.devlang="NA" ms.topic="article" ms.tgt_pltfrm="NA" ms.workload="powerbi" ms.date="06/25/2015" ms.author="v-anpasi"/>
# Marketo content pack for Power BI
[← Services in Power BI](https://support.powerbi.com/knowledgebase/topics/88770-services-in-power-bi)

﻿The Power BI content pack for Marketo allows you to gain insights into your Marketo account with data around Leads and their activities.  
Creating this connection retrieves your data and automatically provides a dashboard and related reports based on that data.  

**Requirements**:  

- The Marketo account you use for connecting has permission to access leads and activities.
- Sufficient API calls available to connect to the data.  Marketo has an API for each account.  When the limit is reached, you won't be able to load data into Power BI Preview.

1. Select **Get Data** at the bottom of the left navigation pane.
	
	![](media/powerbi-content-pack-marketo/PBI_GetData.png)

2.  In the **Services** box, select **Get**.
    
	![](media/powerbi-content-pack-marketo/PBI_GetServices.png) 

3.  Select Marketo > Connect.
    
	![](media/powerbi-content-pack-marketo/PBI_GetMarketoDescriptn.png)
    
4.  Enter the Marketo REST endpoint supplied to you by Marketo or your Marketo admin, and select Next.

    ![](media/powerbi-content-pack-marketo/PBI_MarketoConnect.png)

	Read more about the Marketo REST endpoint: [http://developers.marketo.com/documentation/rest/endpoint-url/](http://developers.marketo.com/documentation/rest/endpoint-url/)

5.  Using the **Basic** Authentication Method, enter the Client ID as the **Username** and the Client Secret as the **Password**. Client ID and Client Secret are available in Marketo or from your marketo admin [(http://developers.marketo.com/documentation/rest/custom-service/)](http://developers.marketo.com/documentation/rest/custom-service/). 

    ![](media/powerbi-content-pack-marketo/PBI_ConfigMarketo.png)

	This gives the *Marketo for Power BI* content pack access to your Marketo data and allows you to analyze the data in Power BI. The data is refreshed once a day.  

6.  Once connected to your Marketo account, a dashboard with all your data is loaded: 

	![](media/powerbi-content-pack-marketo/Marketo_NewDashboard.png)

This dashboard can be fully changed to how you want to display your data. It allows you to ask a [question in](http://support.powerbi.com/knowledgebase/articles/474566-q-a-in-power-bi)[Q&A](http://support.powerbi.com/knowledgebase/articles/474566-q-a-in-power-bi) or click a tile to [open the underlying report](http://support.powerbi.com/knowledgebase/articles/425669-when-you-click-a-tile-in-a-dashboard) and [c](http://support.powerbi.com/knowledgebase/articles/424878-edit-a-tile-resize-move-rename-delete)[](http://support.powerbi.com/knowledgebase/articles/424878-edit-a-tile-resize-move-rename-delete)[hange the tiles](http://support.powerbi.com/knowledgebase/articles/424878-edit-a-tile-resize-move-rename-delete) in the dashboard.

The following data is available from Marketo in Power BI where the activity occurred between today and one year ago:

| Table name     | Description       |
| ---------------|-------------------|
| EmailActivities | Data about email sent to leads/contacts, with details about devices, categories, bounced count and percentage, clicked count and percentage, opened count and percentage, and program name. The Email Activities as shown in Power BI is an absolute email deliverability report, it does not apply any additional logic to the data. You might see some different results between the Marketo client and Power BI because of this.|
| ProgramActivites | Data on programs that have had a change a Status. This includes details such as: Reason, Success, Program acquisition count and percentage, and Program success count and percentage.| 
| WebPageActivities | Data from user web page visits, including search agent, User agent, web page and hour of day.|
| Datetable | Dates from today and the past year.  Allows you to analyze your Marketo data by date. |
| Leads | Lead information like company, revenue size, number of employees,   country, industry, Lead score and Lead status. The leads are retrieved based on their presence in the email, program, and webpage activities data.|

All dates are in UTC. Depending on which time zone your account is in, dates my vary (similar as is seen in the Marketo client)

### API Limit Details

Importing data from Marketo uses Marketo APIs. Every customer of Marketo has a total limit of 10,000 API calls per day that are shared between all applications that use the Marketo APIs. You may use the APIs for other integrations as well as the Power BI integration. For more information on the APIs see: <http://developers.marketo.com/documentation/rest/>.

The amount of API calls Power BI makes to Marketo depends on the amount of data in your Marketo account. Power BI imports all Leads and Activities for the last year. Here is an example of data from Marketo and the amount of API calls that are used by Power BI when importing:

| Data Type      | Number of Rows    | API Calls |
|----------------|-------------------|----------|
|Leads information|15,000|50|
|Mail activities|150,000|1,000|
|Program activities|15,000|100|
|Web activities|150,000|1,000|
|Program changes|7,500|50|
|**Total API Calls**|-|**2,200**|
 

### See Also:

[Get started with Power BI Preview](http://support.powerbi.com/knowledgebase/articles/430814-get-started-with-power-bi)  
[Get Data for Power BI Preview](http://support.powerbi.com/knowledgebase/articles/434354-get-data)  
[Power BI blog: Monitor and analyze your Marketo data with Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/03/19/monitor-and-analyze-your-marketo-data-with-power-bi.aspx)