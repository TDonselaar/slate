---
title: Open-Display API

language_tabs:
  - json: Json
  - javascript: Angularjs

toc_footers:
 

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](http://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

# Authenticate
## auth


```json
    "RequestData":{
        "AppID": "", 
        "Key":"" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odAuthenticate",function(odAuthenticate){
    var data = {
        "AppID": "", 
        "Key":"" };
    odAuthenticate.auth(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## check

```json
    "RequestData":{ }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odAuthenticate",function(odAuthenticate){
    odAuthenticate.check().then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## logout

```json
    "RequestData":{ }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odAuthenticate",function(odAuthenticate){
    odAuthenticate.logout().then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Account
## update

```json
    "RequestData":{
        "FirstName": "",
        "LastName": "",
        "OrganizationName": "",
        "StreetAddress": "",
        "City": "",
        "Country": "",
        "Lang": "",
        "Zip": "",
        "State": "",
        "PhoneNumber": ""
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odAccount",function(odAccount){
    var data = {
        "FirstName": "",
        "LastName": "",
        "OrganizationName": "",
        "StreetAddress": "",
        "City": "",
        "Country": "",
        "Lang": "",
        "Zip": "",
        "State": "",
        "PhoneNumber": ""
        };
    odAccount.update(data).then(function(response) {
        //out put the result in the console
        console.log(response);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## updatePassword

```json
    "RequestData":{
        "OldPassword": "",
        "Newpassword1": "",
        "Newpassword2": ""
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odAccount",function(odAccount){
    var data = {
        "OldPassword": "",
        "Newpassword1": "",
        "Newpassword2": ""
        };
    odAccount.updatePassword(data).then(function(response) {
        //out put the result in the console
        console.log(response);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## info

```json
    "RequestData":{ }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                "Info": {
                    "UserName": "useremail@domain.com",
                    "FirstName": "",
                    "LastName": "",
                    "OrganizationName": "",
                    "StreetAddress": "",
                    "City": "",
                    "Country": "",
                    "Lang": "",
                    "Zip": "",
                    "State": "",
                    "PhoneNumber": "",
                    "EditorTheme": "",
                    "SupportURL": "",
                    "Branding": { "CSS": "", "Title": "" },
                    "Active": "1"
                },"Stats": {
                    "DiskSpace": 0,
                    "DiskSpaceLimit": 5368709120,
                    "Files": 0,
                    "FilesLimit": -1,
                    "Devices": 0,
                    "DevicesLimit": -1,
                    "Playlists": 0,
                    "PlaylistsLimit": -1,
                    "Slides": 0,
                    "SlidesLimit": -1,
                    "Apps": 0,
                    "AppsLimit": -1,
                    "SubUsers": 1,
                    "SubUsersLimit": -1,
                    "Groups": 0,
                    "GroupsLimit": 100,
                    "Domains": 0,
                    "DomainsLimit": 5,
                    "Campaign": 0,
                    "CampaignLimit": 0,
                    "FileFolders": 0,
                    "FileFoldersLimit": -1,
                    "DeviceFolders": 0,
                    "DeviceFoldersLimit": -1,
                    "SlideFolders": 0,
                    "SlideFoldersLimit": -1
                }
            }
        }
```

```javascript
app.controller("SampleController", ["odAccount",function(odAccount){
    odAccount.info().then(function(response) {
        //out put the result in the console
        console.log(response);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## updateSettings

```json
    "RequestData":{ "Class": "Main", "Data": {}}
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odAccount",function(odAccount){
    var data = { "Class": "Main", "Data":{ } };
    odAccount.updateSettings(data).then(function(response) {
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## settings

```json
    "RequestData":{ "Class": "Main" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odAccount",function(odAccount){
    var data = { "Class": "Main" };
    odAccount.settings(data).then(function(response) {
        //get the settings of the class Main
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```


# Application
## create

```json
    "RequestData":{ 
        "Name": "", 
        "AppURL":"", 
        "AppAbout": "" 
    }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odApplication",function(odApplication){
    var data = {
        "Name": "", 
        "AppURL":"", 
        "AppAbout": "" };
    odApplication.create(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{ 
        "ID": "",
        "Name": "", 
        "AppURL":"", 
        "AppAbout": "" 
    }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odApplication",function(odApplication){
    var data = {
        "ID": "",
        "Name": "", 
        "AppURL":"", 
        "AppAbout": ""  };
    odApplication.update(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove

```json
    "RequestData":{ 
        "ID": ""
    }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody": []
        }
```

```javascript
app.controller("SampleController", ["odApplication",function(odApplication){
    var data = {
        "ID": "" };
    odApplication.remove(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{ }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[
                    {   
                        "AppID":"", 
                        "Groups":[], 
                        "About":"", 
                        "Name":"", 
                        "Default": false, 
                        "Owner": false, 
                        "URL":""
                    }
                ]
        }
```

```javascript
app.controller("SampleController", ["odApplication",function(odApplication){
    odApplication.list().then(function(response) {
       //list apps in console
       console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## devList

```json
    "RequestData":{ }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[
                    {   
                        "ID": "", 
                        "PrivateKey": "", 
                        "URL": "", 
                        "Name":"",
                        "About":"",
                        "CreationTime":""
                    }
                ]
        }
```

```javascript
app.controller("SampleController", ["odApplication",function(odApplication){
    odApplication.devList().then(function(response) {
       //list apps in console
       console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## setGroup

```json
    "RequestData":{ "ID": "", "Groups": [] }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odApplication",function(odApplication){
    var data ={ "ID": "", "Groups": [] };
    odApplication.setGroup(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```


## revokeAccess

```json
    "RequestData":{ "ID": "" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odApplication",function(odApplication){
    var data = { "ID": "" };
    odApplication.revokeAccess(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Device
## create

```json
    "RequestData":{ 
        "Key": "", 
        "Name": "", 
        "Tree": 0, 
        "Tags": [] 
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = { 
        "Key": "", 
        "Name": "", 
        "Tree": 0, 
        "Tags": [] 
        };
    odDevice.create(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Tags",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Tree",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                "Count": 0,
                "Items":[{
                    "ID": "",
                    "hl": "",
                    "Date": "2015-03-24",
                    "Time": "1427795611",
                    "Active": "1",
                    "Name": "",
                    "TimeStamp": "1429700587",
                    "DeviceUpTime": 94230,
                    "Group": null,
                    "Tags": [ { Name: "" } ],
                    "Info": {
                    "Status": {
                        "InSync": true,
                        "Restarting": false,
                        "ClearingDate": false
                    },
                    "Info": {
                            "Width":1280,
                            "Height":800,
                            "Time":"Mar 31, 2015 11:53:32 AM",
                            "UpTime":94230,
                            "DiskSize":2147483647,
                            "DiskUsed":40304,
                            "Ethernet":true,
                            "Device":"m1008",
                            "Battery":"",
                            "AndroidFirmware":"4.2.2",
                            "IP":"192.168.1.36",
                            "ThemeID":"1447",
                            "DNS":"8.8.4.4",
                            "Gateway":"192.168.1.1",
                            "Netmask":"255.255.255.0",
                            "AppVersion":"1717",
                            "WIFI_MBPS":24,
                            "WIFI_SSID":"",
                            "SSOSEvent":false,
                            "WIFI_Strength":99,
                            "City":"",
                            "Country":"",
                            "Region":""
                        }
                    },
                    "Preview":"",
                    "Settings":{
                            "Restart":true,
                            "DataClear":false,
                            "AllowOptions":true,
                            "AllwaysOn":true,
                            "ShowSyntaxCheck":false,
                            "ShowBrand":false,
                            "ScreenOffNoTheme":false,
                            "SSOS_Trigger":0,
                            "SSOS_themeid":0,
                            "Orientation":0,
                            "Alpha":0,
                            "DeviceVolume":-1,
                            "IconControl":"1"
                    }
            }]
            }
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Tags",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Tree",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odDevice.list(data).then(function(response) {
       //list device
       console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove

```json
    "RequestData":{ 
        "ID": ""
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = { 
       "ID": ""
        };
    odDevice.remove(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## info

```json
    "RequestData":{ 
        "ID": ""
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                    "ID":"",
                    "Name": "",
                    "hl":"",
                    "Date":"",
                    "Time":"",
                    "Active": "",
                    "Tree": "",
                    "Playlists":[],
                    "PlaylistsByNode":[],
                    "Settings":{
                            "Restart":true,
                            "DataClear":false,
                            "AllowOptions":true,
                            "AllwaysOn":true,
                            "ShowSyntaxCheck":false,
                            "ShowBrand":false,
                            "ScreenOffNoTheme":false,
                            "SSOS_Trigger":0,
                            "SSOS_themeid":0,
                            "Orientation":0,
                            "Alpha":0,
                            "DeviceVolume":-1,
                            "IconControl":"1"
                    },
                    "Info":{
                        "InSync": true,
                        "Restarting": false,
                        "ClearingDate": false
                    },
                    "Info": {
                            "Width":1280,
                            "Height":800,
                            "Time":"Mar 31, 2015 11:53:32 AM",
                            "UpTime":94230,
                            "DiskSize":2147483647,
                            "DiskUsed":40304,
                            "Ethernet":true,
                            "Device":"m1008",
                            "Battery":"",
                            "AndroidFirmware":"4.2.2",
                            "IP":"192.168.1.36",
                            "ThemeID":"1447",
                            "DNS":"8.8.4.4",
                            "Gateway":"192.168.1.1",
                            "Netmask":"255.255.255.0",
                            "AppVersion":"1717",
                            "WIFI_MBPS":24,
                            "WIFI_SSID":"",
                            "SSOSEvent":false,
                            "WIFI_Strength":99,
                            "City":"",
                            "Country":"",
                            "Region":""
                        }
                    }
            }
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = { 
       "ID": ""
        };
    odDevice.remove(data).then(function(response) {
       //get device info
       console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{ 
        "ID": "",
        "Name": "",
        "DeviceVolume": "",
        "SSOS_Trigger": "",
        "SSOS_themeid": "",
        "Alpha": "",
        "Tree": "",
        "Restart": "",
        "DataClear": "",
        "AllowOptions": "",
        "Orientation": "",
        "IconControl": ""
    }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = { 
        "ID": "",
        "Name": "",
        "DeviceVolume": "",
        "SSOS_Trigger": "",
        "SSOS_themeid": "",
        "Alpha": "",
        "Tree": "",
        "Restart": "",
        "DataClear": "",
        "AllowOptions": "",
        "Orientation": "",
        "IconControl": ""
    };
    odDevice.update(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## setFolder

```json
    "RequestData":{ "IDS":[] }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = { "IDS":[] };
    odDevice.setFolder(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## rebootReset

```json
    "RequestData":{ "IDS":[], "Reboot": true, "Reset": true }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = { "IDS":[], "Reboot": true, "Reset": true };
    odDevice.rebootReset(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## updateGlobalSettings

```json
    "RequestData":{ 
                    "CAM_activation":"", 
                    "CAM_sensitivity":"", 
                    "CAM_scaninterval":"", 
                    "SCREEN_powerloss_fade":"", 
                    "SOUND_volume":"",
                    "SystemKeycode":""
                  }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = { 
                "CAM_activation":"", 
                "CAM_sensitivity":"", 
                "CAM_scaninterval":"", 
                "SCREEN_powerloss_fade":"", 
                "SOUND_volume":"",
                "SystemKeycode":""
               };
    odDevice.updateGlobalSettings(data).then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## globalSettings

```json
    "RequestData":{}
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                "CAM_activation":0, 
                "CAM_sensitivity":8, 
                "CAM_scaninterval":2500, 
                "SCREEN_powerloss_fade":1, 
                "SOUND_volume":100, 
                "SystemKeycode":""
            }
        }
```

```javascript
app.controller("SampleController", ["odDevice",function(odDevice){
    var data = {};
    odDevice.globalSettings(data).then(function(response) {
       //get the settings
       console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# DeviceFolders
## create

```json
    "RequestData":{ "Name":"", "ParentID":"" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDeviceFolders",function(odDeviceFolders){
    var data = { "Name":"", "ParentID":"" };
    odDeviceFolders.create(data).then(function(response) {
      
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{  }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                    "Node":{
                        "ID":"",
                        "ParentID":"",
                        "Name":"",
                        "AccountID":"",
                        "Group":"",
                        "Domain":""
                    },"Access":true, 
                    "Nodes": []
            }
        }
```

```javascript
app.controller("SampleController", ["odDeviceFolders",function(odDeviceFolders){

    odDeviceFolders.list().then(function(response) {
      //list the folder
      console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove

```json
    "RequestData":{ "ID":"" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDeviceFolders",function(odDeviceFolders){
    var data = { "ID":"" };
    odDeviceFolders.remove(data).then(function(response) {
      
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{ "ID":"", "Name":"", "ParentID":"" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDeviceFolders",function(odDeviceFolders){
    var data = { "ID":"", "Name":"", "ParentID":"" };
    odDeviceFolders.update(data).then(function(response) {
      
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Files
## list

```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "ID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Width",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Height",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Type",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Status",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "TimeStamp",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                "Count": 0,
                "Items":[{
                    "ID":"",
                    "DID":"",
                    "SubAccountID":"",
                    "Name":"",
                    "Extension":"",
                    "Size":"",
                    "Time":"",
                    "TimeStamp":"",
                    "UnixTimeStamp":"",
                    "Width":"",
                    "Height":"",
                    "Type":"",
                    "Status":"",
                    "Group":[],
                    "StatusCode":"",
                    "Download":"",
                    "URL":"",
                    "Thumbnail":""
                }] }
        }
```

```javascript
app.controller("SampleController", ["odFiles",function(odFiles){
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "ID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Width",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Height",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Type",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Status",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "TimeStamp",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odFiles.update(data).then(function(response) {
      //show a list of files
      console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove

```json
    "RequestData":{ "ID":"" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odFiles",function(odFiles){
    var data = { "ID":"" };
    odFiles.remove(data).then(function(response) {
      
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## uploadURL

```json
    "RequestData":{ }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{ 
                        "URL":"", 
                        "UI":"" 
               }
        }
```

```javascript
app.controller("SampleController", ["odFiles",function(odFiles){ 
    odFiles.uploadURL().then(function(response) {
      //get the upload url or ui
      console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# FileFolders
## create

```json
    "RequestData":{"Name": "", "PID":0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odFileFolders",function(odFileFolders){ 
    var data = {"Name": "", "PID":0 };
    odFileFolders.create(data).then(function(response) {
      
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{"ID":0, "Name": "", "PID":0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odFileFolders",function(odFileFolders){ 
    var data = {"ID":0, "Name": "", "PID":0 };
    odFileFolders.update(data).then(function(response) {
      
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{}
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[
                        "Access": true,
                        "Dirs": [],
                        "Group": 0,
                        "ID": "2",
                        "Name": "test",
                        "PID": "0"
            ]
        }
```

```javascript
app.controller("SampleController", ["odFileFolders",function(odFileFolders){ 

    odFileFolders.list().then(function(response) {
      //list dirs
      console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove

```json
    "RequestData":{ "ID":0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odFileFolders",function(odFileFolders){ 
    var data = { "ID":0 };
    odFileFolders.remove(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# SubUsers
## create

```json
    "RequestData":{ 
                "Username":"", 
                "Password":"", 
                "Group":[], 
                "Domain":[], 
                "FirstName":"", 
                "LastName":"", 
                "OrganizationName":"", 
                "StreetAddress":"", 
                "City":"", 
                "Country":"", 
                "Lang":"", 
                "Zip":"", 
                "State":"", 
                "PhoneNumber":"", 
                "Email":""
               }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSubUsers",function(odSubUsers){ 
    var data = { 
                "Username":"", 
                "Password":"", 
                "Group":[], 
                "Domain":[], 
                "FirstName":"", 
                "LastName":"", 
                "OrganizationName":"", 
                "StreetAddress":"", 
                "City":"", 
                "Country":"", 
                "Lang":"", 
                "Zip":"", 
                "State":"", 
                "PhoneNumber":"", 
                "Email":""
               };
    odSubUsers.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "SubAccountID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Username",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "FirstName",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "LastName",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "OrganizationName",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "StreetAddress",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "City",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Country",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Lang",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Zip",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "State",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "PhoneNumber",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Email",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                "Count": 0,
                "Items":[{ 
                    "ID":"", 
                    "Group": [],
                    "Domain": [],
                    "Username": "",
                    "FirstName": "",
                    "LastName": "",
                    "OrganizationName": "",
                    "StreetAddress": "",
                    "City": "",
                    "Country": "",
                    "Lang": "",
                    "Zip": "",
                    "State": "",
                    "PhoneNumber": "",
                    "Email": "" 
                    }]
                }
        }
```

```javascript
app.controller("SampleController", ["odSubUsers",function(odSubUsers){ 
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "SubAccountID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Username",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "FirstName",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "LastName",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "OrganizationName",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "StreetAddress",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "City",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Country",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Lang",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Zip",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "State",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "PhoneNumber",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Email",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odSubUsers.list(data).then(function(response) {
    //list subusers
      console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{ 
                "ID": 0,
                "Username":"", 
                "Password":"", 
                "Group":[], 
                "Domain":[], 
                "FirstName":"", 
                "LastName":"", 
                "OrganizationName":"", 
                "StreetAddress":"", 
                "City":"", 
                "Country":"", 
                "Lang":"", 
                "Zip":"", 
                "State":"", 
                "PhoneNumber":"", 
                "Email":""
               }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSubUsers",function(odSubUsers){ 
    var data = { 
                "ID": 0,
                "Username":"", 
                "Password":"", 
                "Group":[], 
                "Domain":[], 
                "FirstName":"", 
                "LastName":"", 
                "OrganizationName":"", 
                "StreetAddress":"", 
                "City":"", 
                "Country":"", 
                "Lang":"", 
                "Zip":"", 
                "State":"", 
                "PhoneNumber":"", 
                "Email":""
               };
    odSubUsers.update(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove


```json
    "RequestData":{ "ID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSubUsers",function(odSubUsers){ 
    var data = { "ID": 0 };
    odSubUsers.remove(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## info

```json
    "RequestData":{ "ID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{ 
                    "ID":"", 
                    "Group": [],
                    "Domain": [],
                    "Username": "",
                    "FirstName": "",
                    "LastName": "",
                    "OrganizationName": "",
                    "StreetAddress": "",
                    "City": "",
                    "Country": "",
                    "Lang": "",
                    "Zip": "",
                    "State": "",
                    "PhoneNumber": "",
                    "Email": "" 
                    }
        }
```

```javascript
app.controller("SampleController", ["odSubUsers",function(odSubUsers){ 
    var data = { "ID": 0 };
    odSubUsers.info(data).then(function(response) {
        //get sub user info
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## updatePassword


```json
    "RequestData":{ "ID": 0, "Password":"" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSubUsers",function(odSubUsers){ 
    var data = { "ID": 0, "Password":"" };
    odSubUsers.updatePassword(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Domains
## create

```json
    "RequestData":{ "Name":"" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDomains",function(odDomains){ 
    var data = { "Name":"" };
    odDomains.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "DomainID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                "Count": 0,
                "Items":[{
                            "ID":"", 
                            "Name": ""
                        }]
                }
        }
```

```javascript
app.controller("SampleController", ["odDomains",function(odDomains){ 
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "DomainID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odDomains.list(data).then(function(response) {
        //list domains
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove


```json
    "RequestData":{ "ID":0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDomains",function(odDomains){ 
    var data = { "ID":0 };
    odDomains.remove(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## addUserToDomain


```json
    "RequestData":{ "ID":0, "SubAccountID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDomains",function(odDomains){ 
    var data = { "ID":0, "SubAccountID": 0 };
    odDomains.addUserToDomain(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## removeUserFromDomain


```json
    "RequestData":{ "ID":0, "SubAccountID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odDomains",function(odDomains){ 
    var data = { "ID":0, "SubAccountID": 0 };
    odDomains.removeUserFromDomain(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Groups
## create

```json
    "RequestData":{ "Name": "" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odGroups",function(odGroups){ 
    var data = { "Name": "" };
    odGroups.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "GroupID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                "Count": 0,
                "Items":[{ "ID":0, "Name":"" }]
                }
        }
```

```javascript
app.controller("SampleController", ["odGroups",function(odGroups){ 
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "GroupID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odGroups.list(data).then(function(response) {
        //list groups
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove

```json
    "RequestData":{ "ID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odGroups",function(odGroups){ 
    var data = { "ID":0 };
    odGroups.remove(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## addUserToGroup

```json
    "RequestData":{ "ID":0, "SubAccountID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odGroups",function(odGroups){ 
    var data = { "ID":0, "SubAccountID": 0 };
    odGroups.addUserToGroup(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## removeUserFromGroup

```json
    "RequestData":{ "ID":0, "SubAccountID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odGroups",function(odGroups){ 
    var data = { "ID":0, "SubAccountID": 0 };
    odGroups.removeUserFromGroup(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## updateItem

```json
    "RequestData":{ "Type": "", "Items":[], "Groups":[] }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odGroups",function(odGroups){ 
    var data = { "Type": "", "Items":[], "Groups":[] };
    odGroups.updateItem(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```


# Playlist
## create

```json
    "RequestData":{ 
                "Name":"",
                "Tags":"",
                "Devices":[],
                "GID":"",
                "Tree":"",
                "Random":"",
                "Active":"",
                "Priority":"",
                "DayActive":"",
                "TimeActive":"",
                "DateActive":"",
                "DateFrom":"",
                "DateTo":"",
                "Monday":"",
                "Tuesday":"",
                "Wednesday":"",
                "Thursday":"",
                "Friday":"",
                "Saturday":"",
                "Sunday":"",
                "StartTime":"",
                "EndTime":"",
                "Items":[{ "ID": 0, "Time": 0 }]
             }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odPlaylist",function(odPlaylist){ 
    var data = { 
                "Name":"",
                "Tags":"",
                "Devices":[],
                "GID":"",
                "Tree":"",
                "Random":"",
                "Active":"",
                "Priority":"",
                "DayActive":"",
                "TimeActive":"",
                "DateActive":"",
                "DateFrom":"",
                "DateTo":"",
                "Monday":"",
                "Tuesday":"",
                "Wednesday":"",
                "Thursday":"",
                "Friday":"",
                "Saturday":"",
                "Sunday":"",
                "StartTime":"",
                "EndTime":"",
                "Items":[{ "ID": 0, "Time": 0 }]
             };
    odPlaylist.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "GroupID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Tree",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Type",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Token",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Tags",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                    "Count":1,
                    "Items":[{
                        "ID":1,
                        "SubAccountID":0,
                        "Active":0,
                        "Tree":0,
                        "Tags":[],
                        "GID":0,
                        "Type":1,
                        "Token":"",
                        "Name":"",
                        "Group":[],
                        "Priority":0,
                        "DateActive":0,
                        "DayActive":0,
                        "TimeActive":0,
                        "DateFrom":0,
                        "DateTo":0,
                        "DateLoop":0,
                        "Monday":0,
                        "Tuesday":0,
                        "Wednesday":0,
                        "Thursday":0,
                        "Friday":0,
                        "Saturday":0,
                        "Sunday":0,
                        "StartTime":"07:00",
                        "EndTime":"17:00",
                        "Random":"0"}]
            }
        }
```

```javascript
app.controller("SampleController", ["odPlaylist",function(odPlaylist){ 
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "GroupID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Tree",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Type",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Token",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },
                 { "Key": "Tags",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odPlaylist.list(data).then(function(response) {
        //list playlist
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## listByDevice

```json
    "RequestData":{ "Devices": [] }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                    "Count":1,
                    "Items":[{
                        "ID":1,
                        "SubAccountID":0,
                        "Active":0,
                        "Tree":0,
                        "Tags":[],
                        "GID":0,
                        "Type":1,
                        "Token":"",
                        "Name":"",
                        "Group":[],
                        "Priority":0,
                        "DateActive":0,
                        "DayActive":0,
                        "TimeActive":0,
                        "DateFrom":0,
                        "DateTo":0,
                        "DateLoop":0,
                        "Monday":0,
                        "Tuesday":0,
                        "Wednesday":0,
                        "Thursday":0,
                        "Friday":0,
                        "Saturday":0,
                        "Sunday":0,
                        "StartTime":"07:00",
                        "EndTime":"17:00",
                        "Random":"0"}]
            }
        }
```

```javascript
app.controller("SampleController", ["odPlaylist",function(odPlaylist){ 
    var data = { "Devices": [] };
    odPlaylist.listByDevice(data).then(function(response) {
        //list playlist
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove


```json
    "RequestData":{ "ID": 0, "GID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odPlaylist",function(odPlaylist){ 
    var data = { "ID": 0, "GID": 0 };
    odPlaylist.remove(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update


```json
    "RequestData":{ 
                "ID": 0,
                "Name":"",
                "Tags":"",
                "Devices":[],
                "GID":"",
                "Tree":"",
                "Random":"",
                "Active":"",
                "Priority":"",
                "DayActive":"",
                "TimeActive":"",
                "DateActive":"",
                "DateFrom":"",
                "DateTo":"",
                "Monday":"",
                "Tuesday":"",
                "Wednesday":"",
                "Thursday":"",
                "Friday":"",
                "Saturday":"",
                "Sunday":"",
                "StartTime":"",
                "EndTime":"",
                "Items":[{ "ID": 0, "Time": 0 }]
             }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odPlaylist",function(odPlaylist){ 
    var data = { 
                "ID": 0,
                "Name":"",
                "Tags":"",
                "Devices":[],
                "GID":"",
                "Tree":"",
                "Random":"",
                "Active":"",
                "Priority":"",
                "DayActive":"",
                "TimeActive":"",
                "DateActive":"",
                "DateFrom":"",
                "DateTo":"",
                "Monday":"",
                "Tuesday":"",
                "Wednesday":"",
                "Thursday":"",
                "Friday":"",
                "Saturday":"",
                "Sunday":"",
                "StartTime":"",
                "EndTime":"",
                "Items":[{ "ID": 0, "Time": 0 }]
             };
    odPlaylist.update(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## info


```json
    "RequestData":{ "ID": 0, "GID": 0  }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                        "ID":1,
                        "SubAccountID":0,
                        "Active":0,
                        "Tree":0,
                        "Tags":[],
                        "GID":0,
                        "Type":1,
                        "Token":"",
                        "Name":"",
                        "Group":[],
                        "Priority":0,
                        "DateActive":0,
                        "DayActive":0,
                        "TimeActive":0,
                        "DateFrom":0,
                        "DateTo":0,
                        "DateLoop":0,
                        "Monday":0,
                        "Tuesday":0,
                        "Wednesday":0,
                        "Thursday":0,
                        "Friday":0,
                        "Saturday":0,
                        "Sunday":0,
                        "StartTime":"07:00",
                        "EndTime":"17:00",
                        "Random":"0"
                        "Items":[{ "ID":0, "Name": "", "Time": 0, "Preview":"" }]
                    }
        }
```

```javascript
app.controller("SampleController", ["odPlaylist",function(odPlaylist){ 
    var data = { "ID": 0, "GID": 0  };
    odPlaylist.info(data).then(function(response) {
        //list playlist info
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## link

```json
    "RequestData":{ "ID": 0, "Devices": [] }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odPlaylist",function(odPlaylist){ 
    var data = { "ID": 0, "Devices": [] };
    odPlaylist.link(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## unLink


```json
    "RequestData":{ "ID": 0, "Devices": [] }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odPlaylist",function(odPlaylist){ 
    var data = { "ID": 0, "Devices": [] };
    odPlaylist.unLink(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Tags
## create


```json
    "RequestData":{ "Name": "" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odTag",function(odTag){ 
    var data = { "Name": "" };
    odTag.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{ "ID": "",  "Name": "" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odTag",function(odTag){ 
    var data = { "ID": "",  "Name": "" };
    odTag.update(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                            "Count": 0,
                            "Items": [ { "ID": 0 , "Name": "" } ]
                        }
        }
```

```javascript
app.controller("SampleController", ["odTag",function(odTag){ 
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odTag.list(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```


# Slide
## create


```json
    "RequestData":{ "Name": "", "DID": 0, "Width": 1280,  "Height": 720 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = { "Name": "", "DID": 0, "Width": 1280,  "Height": 720 };
    odSlide.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list


```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },{ "Key": "DID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },{ "Key": "Width",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },{ "Key": "Height",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{ 
                        "Count": 0, 
                        "Items": [{
                            "ID": 0,
                            "Name": "",
                            "DID": "0",
                            "Group": [],
                            "Height": "720",
                            "Width": "1280",                         
                            "Preview": "",
                            "Size": "0",
                            "SubAccountID": "0",
                            "Time": "273"}] 
                }
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },{ "Key": "DID",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },{ "Key": "Width",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 },{ "Key": "Height",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odSlide.list(data).then(function(response) {
        //list themes
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove

```json
    "RequestData":{ "ID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = { "ID": 0 };
    odSlide.remove(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{  "ID": 0, "Name": "", "DID": 0, "HTML": "" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = {  "ID": 0, "Name": "", "DID": 0, "HTML": "" };
    odSlide.update(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## get

```json
    "RequestData":{ "ID": 0, "ResizeWidth": 0, "ResizeHeight":0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                        "ID": 0,
                        "Name": "",
                        "Width": 0,
                        "Height": 0,
                        "DID": 0,
                        "HTML": "",
                        "CSS": "",
                        "JS": "",
                        "RenderOutput": "",
                        "Fonts": [],
                        "Files": [],
                        "LogicV1": []
                    }
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = { "ID": 0, "ResizeWidth": 0, "ResizeHeight":0 };
    odSlide.get(data).then(function(response) {
        //list theme data
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## resolutions

```json
    "RequestData":{  }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[{ "Width" => 0, "Height" => 0, "Name" => "" }]
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = {  };
    odSlide.resolutions(data).then(function(response) {
        //list resolutions
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## setDir

```json
    "RequestData":{ "IDS": [], "DID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = { "IDS": [], "DID": 0 };
    odSlide.setDir(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## send

```json
    "RequestData":{ "ID": "", "UserName": "" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = { "ID": "", "UserName": "" };
    odSlide.send(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## getSent


```json
    "RequestData":{  }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[{ 
                        "UserName": "", 
                        "FromAccountID": 0, 
                        "Name": "", 
                        "ID": 0, 
                        "TimeStamp": "", 
                        "Importing": "" }]
                 }
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = {  };
    odSlide.getSent(data).then(function(response) {
        //list themes
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## removeSent

```json
    "RequestData":{ "ID": 0, "AccountID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = { "ID": 0, "AccountID": 0 };
    odSlide.removeSent(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## importSent


```json
    "RequestData":{ "ID": 0, "AccountID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlide",function(odSlide){ 
    var data = { "ID": 0, "AccountID": 0 };
    odSlide.importSent(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# SlideFolders
## create

```json
    "RequestData":{ Name": "", "PID":0  }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlideFolders",function(odSlideFolders){ 
    var data = { Name": "", "PID":0 };
    odSlideFolders.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{ "ID":0, "Name": "", "PID":0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlideFolders",function(odSlideFolders){ 
    var data = { "ID":0, "Name": "", "PID":0 };
    odSlideFolders.update(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{  }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[
                        "Access": true,
                        "Dirs": [],
                        "Group": 0,
                        "ID": "2",
                        "Name": "test",
                        "PID": "0"
            ]
        }
```

```javascript
app.controller("SampleController", ["odSlideFolders",function(odSlideFolders){ 
    var data = {  };
    odSlideFolders.list(data).then(function(response) {
        //list dirs
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove


```json
    "RequestData":{ "ID":0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odSlideFolders",function(odSlideFolders){ 
    var data = { "ID":0 };
    odSlideFolders.remove(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Pop
## create

```json
    "RequestData":{ "Name": "", "FileID": 0, "MinImpressions":0, "TimeLimit": false, "TimeFrom": 0, "TimeTo": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odPop",function(odPop){ 
    var data = { "Name": "", "FileID": 0, "MinImpressions":0, "TimeLimit": false, "TimeFrom": 0, "TimeTo": 0 };
    odPop.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{ "ID":0, "Name": "", "MinImpressions":0, "TimeLimit": false, "TimeFrom": 0, "TimeTo": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odPop",function(odPop){ 
    var data = { "ID":0, "Name": "", "MinImpressions":0, "TimeLimit": false, "TimeFrom": 0, "TimeTo": 0  };
    odPop.update(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## remove

```json
    "RequestData":{ "ID":0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odPop",function(odPop){ 
    var data = { "ID":0 };
    odPop.remove(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list


```json
    "RequestData":{ "ID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{ 
                    "Count": 0, 
                    "Items": [{
                        "AccountID": "",
                        "Devices": 0,
                        "Impressions": 0,
                        "Seconds": 0,
                        "URL": "",
                        "file_id": "",
                        "id": "",
                        "min_impressions": 0,
                        "name": "",
                        "time_from": "",
                        "time_limit": "",
                        "time_to": ""}] 
                }
        }
```

```javascript
app.controller("SampleController", ["odPop",function(odPop){ 
    var data = { "ID": 0 };
    odPop.list(data).then(function(response) {
        //list pop items
       console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## stats


```json
    "RequestData":{ "ID": 0, "Year": "", "Month": "" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{ 
                "Info": {
                    "AccountID": "",
                    "URL": "",
                    "file_id": "",
                    "id": "",
                    "min_impressions": "",
                    "name": "",
                    "time_from": "",
                    "time_limit": "",
                    "time_to": "",
                },"Stats": [{ 
                    "Date": "2015-05-09",
                    "Devices": 1,
                    "Impressions": 4,
                    "Time": 32 }]
                }
        }
```

```javascript
app.controller("SampleController", ["odPop",function(odPop){ 
    var data = { "ID": 0, "Year": "", "Month": "" };
    odPop.stats(data).then(function(response) {
        //pop stats
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Wads
## remove

```json
    "RequestData":{ "ID": "" }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odWads",function(odWads){ 
    var data = { "ID": "" };
    odWads.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{  }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[{
                    "AccountID": ""
                    "AuthKey": ""
                    "Create_TimeStamp": ""
                    "Main": ""
                    "Name": ""
                    "Update_TimeStamp": ""
                    "Version": ""
                    "id": ""}]
        }
```

```javascript
app.controller("SampleController", ["odWads",function(odWads){ 
    var data = {  };
    odWads.create(data).then(function(response) {
        //list web apps
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Log
## list

```json
    "RequestData":{ "Action": "", "Value": "", "Start": 0, "Limit": 25 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{ 
                    "Count": 0, 
                    "Items": [{
                        "AccountID": 0
                        "Action": ""
                        "AdminUser": 0
                        "SubAccountID": 0
                        "Time": 0
                        "Value": {}
                        }] 
                }
        }
```

```javascript
app.controller("SampleController", ["odLog",function(odLog){ 
    var data = { "Action": "", "Value": "", "Start": 0, "Limit": 25 };
    odLog.list(data).then(function(response) {
        //list actions
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## login

```json
    "RequestData":{ "LoginError": false, "Start": 0, "Limit": 25 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{ 
                    "Count": 0, 
                    "Items": [{
                        "IP': "",
                        "LocationCity": "",
                        "LocationCountry": "",
                        "LocationRegion": "",
                        "LoginCounts": "0",
                        "ResetTime": "0",
                        "TimeStamp": 0,
                        "Username": "",
                        }] 
                }
        }
```

```javascript
app.controller("SampleController", ["odLog",function(odLog){ 
    var data = { "LoginError": false, "Start": 0, "Limit": 25 };
    odLog.login(data).then(function(response) {
        //list logs
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

# Feed
## create

```json
    "RequestData":{ 
                "Name": "", 
                "Settings": {"FontSize":"32", "FontColor":"Black", "BackgroundColor":"none"} ,
                "Feed": [{ "title": "", "description": "" }],
                "AutoInsert": false
            }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odFeed",function(odFeed){ 
    var data = { 
                "Name": "", 
                "Settings": {"FontSize":"32", "FontColor":"Black", "BackgroundColor":"none"} ,
                "Feed": [{ "title": "", "description": "" }],
                "AutoInsert": false
            };
    odFeed.create(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## update

```json
    "RequestData":{ 
                "ID": 0,
                "Name": "", 
                "Settings": {"FontSize":"32", "FontColor":"Black", "BackgroundColor":"none"} ,
                "Feed": [{ "title": "", "description": "" }],
                "AutoInsert": false
            }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odFeed",function(odFeed){ 
    var data = { 
                "ID": 0,
                "Name": "", 
                "Settings": {"FontSize":"32", "FontColor":"Black", "BackgroundColor":"none"} ,
                "Feed": [{ "title": "", "description": "" }],
                "AutoInsert": false
            };
    odFeed.update(data).then(function(response) {

    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## list

```json
    "RequestData":{ 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                "Count": 0,
                "Items":[{
                    "ID":"",
                    "Name":"",
                    "Group":[],
                    "AutoInser":""
                }]
            }
        }
```

```javascript
app.controller("SampleController", ["odFeed",function(odFeed){ 
    var data = { 
        "ResultsStart":0,
        "ResultsLimit":25,
        "Filter":[
                 { "Key": "Name",
                   "Selector":"and",
                   "Operator":"=",
                   "Sort":"ASC", 
                   "Value":""
                 }
              ]
        };
    odFeed.list(data).then(function(response) {
        //list feeds
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```

## info

```json
    "RequestData":{ "ID": 0 }
```

```json
    "Response":{ 
            "ApiInfo":{
                "ApiVersion":"2",
                "ServerTime":1430387863
            },"Session":{
                "Token":"",
                "UserType":"User",
                "SubAccountID":0,
                "AccountID":"60",
                "UserName":"useremail@domain.com"
            },"ResponseHead":{
                "Code":200,
                "Message":"OK"
            },"ResponseBody":{
                        "ID": "",
                        "Name": "",
                        "Settings": {"FontSize":"32", "FontColor":"Black", "BackgroundColor":"none"} ,
                        "Feed": [{ "title": "", "description": "" }],
                        "AccountID": "",
                        "Group": [],
                        "AutoInsert": ""}
        }
```

```javascript
app.controller("SampleController", ["odFeed",function(odFeed){ 
    var data = { "ID": 0 };
    odFeed.info(data).then(function(response) {
        //get feed info
        console.log(response.ResponseBody);
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
}]);
```