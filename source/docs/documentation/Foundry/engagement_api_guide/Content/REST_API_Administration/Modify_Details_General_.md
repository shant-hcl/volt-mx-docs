---
layout: "documentation"
category: "engagement_api_guide"
---
                            


Modify Details(General)
=======================

The **Modify Details (General)** API, based on a request modifies basic engagement services configuration.

URL
---

The HTTP URL for **Modify Details (General)** API is:

{% highlight voltMx %}http://<host>:<port>/api/v1/admin
{% endhighlight %}

This service implements Gateway Filter for Authentication to authenticate access of the service by a user.

Method
------

PUT

Header
------

The payload's request header includes Content-Type as application/json;charset=UTF-8.

Input Parameters
----------------

The following fields are input parameters:

  
| Input Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| retriesPerNotification | Yes | N/A | Configuring the number from 1 to 10 indicates that Engagement Server retries to send a push message to a subscriber in a day to the restricted number. Maximum Retries per Notification is up to 10 |
| reconciliationKey | Yes | String | Key with which messages are sent. When you create or update a **[user](../REST_API_Audience_Member/Create_AudienceMemebrs.html)**, if parameter **mobileNumber** is specified as the reconciliation key, then **mobileNumber** is a required value and must be specified for all users. An empty value will cause an error. |
| campaignExecutionIntervel | Yes | long | Based on the specified time, Engagement server checks for sending campaign message |
| preferredTimeZone | Optional | string | Time Zones are a geographical world globe division starting at Greenwich, in England. You can set a time zone for times and dates according to your locale |
| keyId | Optional | string | It is a 10-character string. Get the keyId of your app from your Apple Developer Account. |
| teamId | Optional | string | It is a unique 10-character string associated with an Apple Developer Account. Get the teamId of your app from your Apple Developer Account. |
| apnsProviderPrivateKey | Optional | string | It is a unique key that is generated when you create an APNS certificate. Get the apnsProviderPrivateKey of your app from your Apple Developer Account. |

> **_Important:_** If you want to enable Token-Based Connection, you must provide the keyId, teamId, and apnsProviderPrivateKey.

Sample Request
--------------

{% highlight voltMx %}{  
  "retriesPerNotification" : 9,  
  "reconciliationKey" : "Email",  
  "campaignExecutionIntervel" : 1,  
  "preferredTimeZone" : "GMT+05:30"
  "keyId" : "5M80QD7GB2"
  "teamId" : "DP7853I8YE"
  "apnsProviderPrivateKey" : "MIGTAgEAMBMGByqGSM49AgEGCCqGSM49AwEHBHkwdwIBAQQgQ
3iDy26Mx6diayfNhjUaANGv0k95tye45hWCC6wN/oOgCgYIKoZIzj0DAQehRANCAAQ6hwi1Iouod8gF
UG9+AD95RpQOpWrmbCGaB7HjSbXuyigkx2wlYVxiTgV//fqQZVGpXYrW0gUruiAe+Ej5JQxy"  
}  

{% endhighlight %}

Sample Response
---------------

{% highlight voltMx %}{  
   "message" : "Successfully Updated the details. ",  
   "id" : ""  
}  

{% endhighlight %}

Response Status
---------------

  
| Code | Description |
| --- | --- |
| Status 200 | Successfully updated the details |
| Status 400 | Invalid request. Request method not allowedValue for reconcilationKey should be one of : \[email, mobile number\]Value for reconciliationKey can not be empty |
| Status 401 | Unauthorized request |
| Status 500 | Server failure to process request |

<table class="TableStyle-RevisionTable" cellspacing="0" style="margin-left: 0;margin-right: auto;mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">7.1</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">AU</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">Au</td></tr></tbody></table>
