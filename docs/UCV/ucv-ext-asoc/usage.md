
HCL AppScan on Cloud (ASoC) - Usage
===================================

# Usage



### Usage






To use the HCL AppScan on Cloud plug-in, the plug-in must be loaded and an instance created before you 
can configure the plug-in integration. You define configuration properties in the user interface or in a JSON file. To 
invoke the plug-in, you must send an HTTP Post to request the plug-in endpoint.



### **Define integration**


The 
value stream map contains the properties, you will use to define the plug-in integration. Basically, the plug-in 
integration is defined with a value stream within the UrbanCode Velocity user interface. Defining the integration 
includes defining [configuration properties](#integration) that connect the UrbanCode Velocity server to the Application
 Security On Cloud server.


To define the integration, the basic flow includes:


1. Download the value stream map. The
 value stream map is a JSON file used to define integrations.
2. Edit the JSON file to include the plug-in configuration
 properties.
3. Save and upload the JSON file. This replaces the current JSON file with the new content.
4. View the new
 integration on the Integration user interface page.


### **Send HTTP Post**


To gather data, send an HTTP POST 
request to your endpoint:



```

https:///pluginEndpoint//asocScan

```

The payload for this POST is `{"scanId":"", 
"buildUrl": ""}```.


1. scanId – The scan id from the scan ran in ASoC. It is a mandatory field to render the scan 
results in Insights
2. buildUrl – The build URL from Jenkins or any other CI/CD tool. It is an optional field which 
links the ASoC scan results with VSM


Integration type
----------------


The AppScan On Cloud plug-in supports 
endpoint integration which are listed in the following table.




| Name | Path | Method |
| --- | --- | --- |
| ASoC 
Scan | asocScan | Post |


Integration
-----------


From the user interface Value Steam page, click **Upload** to 
upload the value stream map which is a JSON file.


The JSON file contains the information for creating a value stream 
and integrating with the Application Security on Cloud server. The following table describes the information for the 
creating a UrbanCode Velocity value stream map.




| Name | Description | Required |
| --- | --- | --- |
| image | The 
version of the plug-in that you want to use. To view available versions, see the [UrbanCode 
DockerHub](https://hub.docker.com/r/urbancode/ucv-ext-asoc/tags). If a value is not specified, the latest version is 
used. | No |
| name | An assigned name to the value stream. | Yes |
| properties | List of [configuration 
properties](#properties) used to connect and communicate with the Application Security on Cloud server. Enclose the 
properties within braces. | Yes |
| tenant\_id | The name of the tenant. | Yes |
| type | Unique identifier assigned to 
the plug-in. The value for the Application Security On Cloud plug-in is `asocPlugin` | Yes |


### Configuration 
Properties


The configuration properties which are included in the `properties` field are unique to the Application 
Security On Cloud plug-in and define the connection and communication to the Application Security On Cloud server.




|
 Name | Type | Description | Required | Property Name |
| --- | --- | --- | --- | --- |
| Key ID | String | The key ID 
to authenticate with the Application Security On Cloud server. | Yes | keyId |
| URL | String | The URL of the 
Application Security on Cloud server. | Yes | asocUrl |
| Key Secret | Secure | The key secret to authenticate with the 
Application Security On Cloud server. | Yes | keySecret |
| UrbanCode Velocity User Access Key | Secure | The user 
access key to authenticate with the UrbanCode Velocity server. | Yes | ucvAccessKey |


Example
-------


The following 
example can be used as as template to include the AppScan On Cloud plug-in integration into the JSON file. Copy and 
paste the template into the JSON file and make the appropriate changes.



```

"integrations": [
  {
    "type": 
"asocPlugin",
    "tenant_id": "",
    "name": "",
    "properties":{
      "ucvAccessKey": "",
      "keyId" : "",

      "keySecret":"",
      "asocUrl":""
    }``
 }``
]

```

 




|Back to ...||Latest Version|HCL AppScan on Cloud (ASoC) |||
| :---: | :---: | :---: | :---: | :---: | :---: |
|[All Plugins](../../index.md)|[Velocity Plugins](../README.md)|[3.0.5]()|[Readme](README.md)|[Overview](overview.md)|[Downloads](downloads.md)|