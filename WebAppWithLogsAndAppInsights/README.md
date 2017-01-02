
The **WebAppWithLogsAndAppInsights** project contains an ARM template which specifies the folloowing resources:

1.  a Web App hosting plan
2.  a Web App
    * the Web App configuration
    * the Web App application settings
    * the Web App connection strings
    * the Web App logs configuration
    * the web app Azure Web Site Logs Browser extension
    * the web app Application Insights extension
3.  Application Insights auto scale settings for the Web App hosting plan
4. Application Insights server errors alert rules for the Web App 
5. Application Insights forbidden requests alert rules for the Web App 
6. Application Insights cpu high alert rules for the Web App hosting plan
7. Application Insights long http queue alert rules for the Web App hosting plan
8. Application Insights to monitor the Web App
