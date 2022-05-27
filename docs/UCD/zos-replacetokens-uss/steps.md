
z/OS USS Utility - Steps
========================

# Steps



### Steps






Process steps in the Replace Token USS plug-in
----------------------------------------------


* 
[Replace Tokens USS](#replace_tokens_uss)




Replace Tokens USS
------------------


Replace tokens in files using 
properties.




| Name | Type | Description | Required | Property Name |
| --- | --- | --- | --- | --- |
| Custom 
Encoding | String | Specify a character encoding to use. If blank, the replacement file is created with the local 
character encoding of the agent. Example encodings: UTF-8, US-ASCII, UCS-2, JIS X 0201, UTF-16, UTF-16LE, EUC. | No | 
customEncoding |
| Directory Offset | String | The directory relative to the current working directory that contains the
 files to operate on. | No | dir |
| End Token Delimiter | String | The end delimiter character used to identify tokens.
 | No | endDelimiter |
| Exclude Files | String | A list of patterns, separated by commas or spaces, that describe the 
files to exclude. New lines will be replaced with commas. | No | excludes |
| Explicit Tokens | String | A list, 
separated by newline characters, of explicit tokens to replace in the form of @token@->value or token->value. For 
example: if you specify @mytoken@->new\_value, the step replaces @mytoken@ with new\_value. The token delimiter and 
property prefix settings do not apply. If you specified a value in the Property List field, the explicit tokens are 
added as additional values to replace, and override any properties that have the same name. You cannot use regular 
expressions. | No | explicitTokens |
| Include Files | String | A list of patterns, separated by commas or spaces, that 
describe the files to include. New lines will be replaced with commas. | Yes | includes |
| Property File Name | String 
| The name of the file used to store the replacement name-value pairs. You can use an existing file. If the file does 
not exist, it is created and then removed when the step completes. | No | propFile |
| Property List | String | The 
property used to determine the tokens to replace in the target file. For example, if you specify 
``${p:environment/allProperties}`` the names of all component environment properties are used as tokens and the property
 values as the replacements. Similarly, ``${p:component/allProperties}``,``${p:environment/allProperties}`` all 
components and component environment properties are used as tokens. The values specified on Start Token Delimiter and 
Property Prefix propeties apply. For example, if you specify @ for the start and end token delimiters and a property 
named token1 exists, the step searches for @token1@ to replace. | No | envPropValues |
| Property Prefix | String | 
Specify a prefix to use to determine which properties are included in token replacement. Leave blank to include all 
properties. | No | propertyPrefix |
| Start Token Delimiter | String | The start delimiter character used to identify 
tokens. | No | startDelimiter |





|Back to ...||Latest Version|z/OS USS Utility ||||
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|[All Plugins](../../index.md)|[Deploy Plugins](../README.md)|[1.1127592](https://raw.githubusercontent.com/UrbanCode/IBM-UCD-PLUGINS/main/files/zos-replacetokens-uss/ucd-plugins-zos-replacetokens-uss-1.1127592.zip)|[Readme](README.md)|[Overview](overview.md)|[Usage](usage.md)|[Downloads](downloads.md)|