---
layout: "documentation"
category: "engagement_api_guide"
---
                             


Modify Web Details
==================

The **Modify Web Details** API updates the Firebase API key.

URL
---

The HTTP URL for **Modify Web Details** API is:

{% highlight voltMx %}http://<host>:<port>/api/v1/applications/<id>/web
{% endhighlight %}

This service implements Gateway Filter for Authentication to authenticate access of the service by a user.

> **_Note:_** **<id>**: While creating an app, a unique ID is assigned to an application. Provide the unique identifier for the app in REST URL.  

Method
------

POST

Header
------

The payload's request header includes Content-Type as application/json.

Input Parameters
----------------

The following fields are input parameters:

  
| Input Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| webFcmApiKey | Yes | alphanumeric | Firebase Cloud Messaging service sends data from a server to a web application. |

Sample Request
--------------

{% highlight voltMx %}{
  "appId": "300960548252167",
  "applicationName": "SampleApp",
  "categoryName": "Finance",
  "googleApiKey": "AIzaSyBmZDbw2vobnWMAIHU3ozTlNT_tr-m9hUU",
  "webFcmApiKey": "KKASLpd_bmE:KAP01bGkPvkk4G_RLR7XJRC1Y0H3ho8LydR_E5m254zkoL8JYbzvUMGz5GFUgGOIZLG4hKevil1LRZ5G2O
  5LYtu2Q7yZ2QURYKb29SEnN2QHE9IB9QsLM7KBKy2QZFsZrHVH9LHHiB3DvDsK8",
  "blackBerryAppId": "",
  "blackBerryUrl": "",
  "blackBerryAppPwd": "",
  "windows8ClientId": "ms-app://s-1-15-2-213995348-1368721946-2967673374-1428200323-1145738169-1646738291-64223294",
  "windows8ClientSecret": "DJ1uYWdv7gvYAQaVj7v1Kh9UDtecD-6S",
  "windowsPhone7": true,
  "windowsPhone8": true,
  "windows8AuthToken": "",
  "jpushAppKey" : "71d7cde4c164dd3d997f86e1",
  "jpushMasterSecret" : "fad621972177276a4071577d"
}
{% endhighlight %}

Output Parameters
-----------------

The following fields are output parameters:

  
| Output Parameter | Type | Description |
| --- | --- | --- |
| id | long | Unique app ID assigned to an app |
| message | string | Response status message |

Sample Response
---------------

{% highlight voltMx %}{
  "id" : "300960548252167",
  "message" : "Details updated successfully"
}
{% endhighlight %}

Response Status
---------------

  
| Code | Description |
| --- | --- |
| Status 200 | Details updated successfully |
| Status 400 | Invalid appID provided or no application found with provided appID |
| Status 401 | Unauthorized request |
| Status 500 | Server failure to process request |

<table class="TableStyle-RevisionTable" cellspacing="0" style="margin-left: 0;margin-right: auto;mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">8.4</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">DR</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">DR</td></tr></tbody></table>
