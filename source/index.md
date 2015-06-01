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

Welcome to the Open Display API doc.

In this document we describe how to connect and run api functions.
We currently have a angularjs sdk more sdk are in the work. 

# Authentication

We support two ways of authenticating, client side and server side authentication.

First step is to create a new application in your account dashboard. 

Create an app:

-Login to your account dashboard.

-Go to Apps -> Custom Apps -> plus button on the top left.

-Fill in all of the fields. note. the app URL is the URL that the user is redirected once logged in we will put the auth token at the end of this URL.

<b>Client side authentication.</b>

<b>Flow:</b> Redirect user to the login page with the AppID or RedirectURL -> user is redirect back to the app with at the end of the url the auth token.

It is up to the client side application to get the auth token and store it locally on the client's device. This way the application can use the auth token to make api request on behalf of the client. The token has a limited lifespan so when a api request fails due to that the user token is invalid (Return code: 401) restart the authentication flow.


<b>Server side authentication.</b>

<b>Flow:</b> Auth using the private key -> success server returns a token that is valid x number of seconds -> use the token to do api calls on behalf of the app owner.

Once you have created an app you can press the edit icon of the app you will be shown the settings of the app and the <b>private key</b>.

The <b>private key</b> is needed to do server side logins as the owner of the account in which you have created the app.

# Authenticate

## auth

This function is used for server side authentication you will need to send the AppID and private key to the api. 
On server response you will receive the token. this token allows for you to make request on behalf of the client. 

> https://api.open-display.io/webapi/core/Authenticate/Auth

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Authenticate/check

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Authenticate/Logout

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Account/Update

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Account/UpdatePassword

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Account/Info

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Account/UpdateSettings

> POST VARS: Token: {Token id}, RequestData: {json string}

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

## Settings

> https://api.open-display.io/webapi/core/Account/Settings

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Applications/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Applications/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Applications/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Applications/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Applications/DevList

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Applications/SetGroup

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Applications/RevokeAccess

> POST VARS: Token: {Token id}, RequestData: {json string}

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

## accessLevels

> https://api.open-display.io/webapi/core/Applications/AccessLevels

> POST VARS: Token: {Token id}, RequestData: {json string}

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
            },"ResponseBody":[]
        }
```

```javascript
app.controller("SampleController", ["odApplication",function(odApplication){

    odApplication.accessLevels().then(function(response) {
       
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

> https://api.open-display.io/webapi/core/Devices/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Devices/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Devices/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Devices/Info

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Devices/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Devices/SetFolder

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Devices/RebootReset

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Devices/UpdateGlobalSettings

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Devices/GlobalSettings

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/DeviceFolders/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/DeviceFolders/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/DeviceFolders/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/DeviceFolders/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Files/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Files/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Files/UploadURL

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/FilesFolders/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/FilesFolders/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/FilesFolders/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/FilesFolders/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/SubUsers/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/SubUsers/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/SubUsers/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/SubUsers/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/SubUsers/Info

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/SubUsers/UpdatePassword

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Domains/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Domains/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Domains/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Domains/AddUserToDomain

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Domains/RemoveUserFromDomain

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Groups/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Groups/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Groups/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Groups/AddUserToGroup

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Groups/RemoveUserFromGroup

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Groups/UpdateItem

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Playlist/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Playlist/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Playlist/ListByDevice

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Playlist/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Playlist/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Playlist/Info

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Playlist/Link

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Playlist/UnLink

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Tag/New

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Tag/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Tag/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/New

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Slide/List

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/Slide/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/Get

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/Resolutions

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/SetDir

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/Send

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/GetSent

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/RemoveSent

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Slide/Import

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/core/SlideFolders/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/SlideFolders/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/SlideFolders/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/SlideFolders/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/pop/Campaign/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/pop/Campaign/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/pop/Campaign/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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
> https://api.open-display.io/webapi/pop/Campaign/List

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/pop/Campaign/Stats

> POST VARS: Token: {Token id}, RequestData: {json string}


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

> https://api.open-display.io/webapi/wads/WADS/Remove

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/wads/WADS/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Log/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Log/Login

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Feed/New

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Feed/Update

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Feed/List

> POST VARS: Token: {Token id}, RequestData: {json string}

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

> https://api.open-display.io/webapi/core/Feed/Info

> POST VARS: Token: {Token id}, RequestData: {json string}

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

