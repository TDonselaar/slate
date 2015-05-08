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

# Authenticate
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
            },"ResponseBody":[{
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
            }]
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
            },"ResponseBody":[
                    { 
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
            ]
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
## list
## remove
## addUserToDomain
## removeUserFromDomain

# Groups
## create
## list
## remove
## addUserToGroup
## removeUserFromGroup
## updateItem

# Playlist
## create
## list
## listByDevice
## remove
## update
## info
## link
## unLink

# Tags
## create
## update
## list

# Slide
## create
## list
## remove
## update
## get
## resolutions
## setDir
## send
## getSent
## removeSent
## importSent

# SlideFolders
## create
## update
## list
## remove

# Pop
## create
## update
## remove
## list
## stats

# Wads
## create
## update
## remove
## list

# Rights
## update
## list
## values

# Campaign
## create
## update
## remove
## list
## copy

# Questions
## create
## update
## remove
## list

# Log
## list
## login

# Feed
## create
## update
## list
## info

# Wads
## update
## remove
## list