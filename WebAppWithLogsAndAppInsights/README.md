
The **WebAppWithLogsAndAppInsights** project contains an ARM template which specifies the following resources:

1.  a Web App hosting plan
2.  a Web App
    * the Web App configuration
    * the Web App application settings
    * the Web App connection strings
    * the Web App logs configuration
    * the web app Azure Web Site Logs Browser extension
    * the web app Application Insights extension
3. Application Insights auto scale settings for the Web App hosting plan
4. Application Insights server errors alert rules for the Web App 
5. Application Insights forbidden requests alert rules for the Web App 
6. Application Insights cpu high alert rules for the Web App hosting plan
7. Application Insights long http queue alert rules for the Web App hosting plan
8. Application Insights to monitor the Web App

This template configures the Web App to log and keep its logs in the file system. It also sets the Web App to be monitored by Application Insights
Notes:

1. Concat vs Resourceid
For at least the Microsoft.Web resource provider the string generated by
    "[concat(resourceGroup().id,'/providers/Microsoft.Web/Sites/', variables('webAppName'), '/config','/web')]"
is the same as
    "[resourceId('Microsoft.Web/Sites/config', variables('webAppName'), 'web')]"

Due to the resourceID function beign simpler to use than the concat function I will try to be consistent at using the resourceID 
function in my resource templates from now on.

2. I found the above by adding a key "resourceid" to the applicxation settings resource properties list and setting its value to 
"[resourceId('Microsoft.Web/Sites/config', variables('webAppName'), 'web')]"

3. The key "clientAffinityEnabled" added to the Web App properties sets the Web App ARR Affinity to false. The ARR Affinity setting is found in the 
Web App Application Settings blade on Azure Portal.
