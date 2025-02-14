---
layout: "documentation"
category: "engagement_api_guide"
---
                            


Create/Modify Subscriber
========================

The **Create/Modify Subscriber** API is used to create a new subscriber and also modify an already existing subscriber.

> **_Important:_** Only Create/Modify Subscriber API is used to create and update a subscriber

URL
---

The HTTP URL for **Create/Modify Subscriber** API is:

{% highlight voltMx %}http://<host>:<port>/api/v1/subscribers
{% endhighlight %}

This service implements Gateway Filter for Authentication to authenticate access of the service by a user.

Method
------

POST

Header
------

The payload's request header includes Content-Type as application/json;charset=UTF-8.

Input Parameters
----------------

The following fields are input parameters:

  
| Input Parameter | Level – Two | Required | Type | Description |
| --- | --- | --- | --- | --- |
| subscriptionService |   |   |   | Includes an array of subscribe |
| subscribe |   |   |   | An array of subscribe objects |
|   | sid | Yes | long | The security ID for the subscriber |
|   | appId | Yes | long | The unique ID assigned to an app |
|   | ufid | Optional | string | The User Friendly Identifier or UFID is used when you subscribe to Volt MX Foundry Engagement Services. Based on your requirement, you can provide a UFID. It is alphanumeric, for example xxx@voltmx.com or 2890XZCY. It can be used to map devices to the user using the value as a reconciliation key |
|   | osType | Yes | string | Supported operating system. |
|   | deviceId | Yes | string | Unique ID assigned to a device. |
|   | deviceName | Optional | string | Name of the device |

Sample Request
--------------

{% highlight voltMx %}{
 "subscriptionService": {
  "subscribe": {
   "sid": "923456XQY",
   "appId": "20096-6548262167",
   "ufid": "aron.hale@voltmx.com",
   "osType": "androidgcm",
   "deviceId": "92345600X",
   "deviceName": "Demo_Device"
  }
 }
}
{% endhighlight %}

> **_Note:_** You need to use specific key words while providing parameters for osType in the sample request. The sample payload for all the osType is given below.

{% highlight voltMx %}            
            {
	"subscriptionService": {
		"subscribe": {
			"sid": "923456XQYL",
			"appId": "25016-9447884208",
			"ufid": "deepak.seth@gmail.com",
			"osType": "iphone or ipad", // For Apple
			"osType": "androidgcm or androidjpush",
			"osType": "blackberry",
			"osType": "windows",// For MPNS subscription
			"osType": "windows8",// For WNS subscription
                       "osType": "webfcm",
			"deviceId": "92345600XZ",
			"deviceName": "Demo_Device"
		}
	}
}
{% endhighlight %}

Sample Responses
----------------

{% highlight voltMx %}{
  "id" : "9073640394665981874",
  "message" : "Subscription successful. "
}
{% endhighlight %}{% highlight voltMx %}{
  "id" : "4927718950329103027",
  "message" : " Update successful. "
}
{% endhighlight %}

Response Status
---------------

  
| Code | Description |
| --- | --- |
| Status 200 | Subscription successful |
| Status 400 | Invalid Volt MX application IDInvalid Request. SID Cannot be emptyError occurred at property subscriptionService->subscribe->osTypeInvalid Request. DEVICEID Cannot be empty |
| Status 401 | Unauthorized request |
| Status 500 | Server failure to process request |

<table class="TableStyle-RevisionTable" cellspacing="0" style="mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">7.1</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">AU</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">DR</td></tr></tbody></table>
