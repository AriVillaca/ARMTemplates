
The **WebAppWithLogsAndAppInsights** project contains an ARM template which specifies the following resources:

1.  a Function App consumption hosting plan
2.  a Function App
    * the Function App configuration
    * the Function App application settings
    * the Function App connection strings
    * the Function App logs configuration
    * the Function app Azure Web Site Logs Browser extension
    * the Function app Application Insights extension
3. Application Insights auto scale settings for the Function App hosting plan
4. Application Insights cpu high alert rules for the Function App hosting plan
5. Application Insights long http queue alert rules for the Function App hosting plan
6. Application Insights to monitor the Web App

This template configures the Function App to log and keep its logs in the file system.
It also sets the Function App to be monitored by Application Insights.

Notes:

1. Application Insights server errors alert rules cannot be used to monitor the Function App 
2. Application Insights forbidden requests alert rules cannot be used to monitor Function App
