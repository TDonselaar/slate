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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odAccount",
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
]);
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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odAccount",
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
]);
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
app.controller("SampleController", ["odAccount",
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
]);
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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odAccount",
    var data = { "Class": "Main", "Data":{ } };
    odAccount.updateSettings(data).then(function(response) {
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
]);
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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odAccount",
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
]);
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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odAuthenticate",
    odAuthenticate.check().then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
]);
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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odAuthenticate",
    odAuthenticate.logout().then(function(response) {
       
    },function(response){
        //on error we show it in the console.
        console.log(
            "Code: "+response.ResponseHead.Code+
            " Message:"+response.ResponseHead.Message
            );
    }); 
]);
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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odApplication",
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
]);
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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odApplication",
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
]);
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
            },"ResponseBody":{
            }
        }
```

```javascript
app.controller("SampleController", ["odApplication",
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
]);
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
app.controller("SampleController", ["odApplication",
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
]);
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
app.controller("SampleController", ["odApplication",
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
]);
```

## categories
## setGroup
## revokeAccess

# Device
## create
## list
## remove
## info
## update
## setNode
## rebootReset
## updateGlobalSettings
## globalSettings

# DeviceFolders
## create
## list
## remove
## update

# Files
## create
## list
## remove
## uploadURL
## download

# FileFolders
## create
## update
## list
## remove

# SubUsers
## create
## list
## update
## remove
## info
## updatePassword

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