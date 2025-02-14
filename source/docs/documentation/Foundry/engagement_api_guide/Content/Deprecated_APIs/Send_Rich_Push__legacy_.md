---
layout: "documentation"
category: "engagement_api_guide"
---
                            


Send Rich Push (legacy)
=======================

The **Send Rich Push (legacy)** API sends a rich push message.

> **_Important:_** The Send Rich Push (legacy) API is maintained here to preserve backward compatibility. We encourage you to use [Send Rich Push](../Push_Message_APIs/Send_Rich_Push.html)

URL
---

The HTTP URL for Send Rich Push (legacy) API is:

{% highlight voltMx %}http://<host>:<port>/message  

{% endhighlight %}

Content Type
------------

Based on the content format, the payload's request header Content-Type for:

*   **XML** is text/xml;charset=UTF-8
*   **JSON** is application/json;charset=UTF-8

Method
------

POST

Input Parameters
----------------

The following fields are input parameters:

  
| Input Parameter | Level- Two | Type | Description |
| --- | --- | --- | --- |
| appId |   | string | Application ID |
| global |   | array | Global descriptors |
| messages |   | array | Contains the message elements for each message |
|   | message | array | Contains the elements for a specific message, including: expiryTimestamp overrideMessageId startTimestamp type subscribers platformSpecificProps content |

Sample Request
--------------

### XML

{% highlight voltMx %}<?xml version="1.0" encoding="utf-8"?>
<messageRequest appId="PushTestApp">
  <global>
    <subscribers/>
    <platformSpecificProps/>
  </global>
  <messages>
    <message expiryTimestamp="0" overrideMessageId="0" refId="" startTimestamp="0" type="PUSH">
      <subscribers>
        <subscriber deviceId="b1f147b2 df184ca8 63b6511e bfd5ce14 5f2bdf1b 8bdade42 afd013d7 2e06509e"/>
      </subscribers>
      <content>
        <mimeType>text/plain</mimeType>
        <priorityAPI>false</priorityAPI>
        <data>sample rich push data from testRichPushIphoneXML_Legacy</data>
        <richContent> sample rich push data</richContent>
      </content>
    </message>
  </messages>
</messageRequest>
{% endhighlight %}

### JSON

{% highlight voltMx %}{
  "messageRequest": {
    "appId": "PushTestApp",
    "global": {},
    "messages": {
      "message": {
        "expiryTimestamp": "0",
        "overrideMessageId": "0",
        "startTimestamp": "0",
        "type": "PUSH",
        "subscribers": {
          "subscriber": {
            "deviceId": "testAndroidGCMDevice"
          }
        },
        "platformSpecificProps": {},
        "content": {
          "mimeType": "text/plain",
          "priorityAPI": "false",
          "data": "sample rich push data from testRichPushAndroidJSON",
          "richContent": {
            "value": "<h1> Sample Mail </h1>Hello,<br><div class=\"float_left\"></div>This is a sample Mail.<br>Regards,<br>VoltMX<br>"
          }
        }
      }
    }
  }
}

{% endhighlight %}

Sample Responses
----------------

### XML

{% highlight voltMx %}<messageResponse>
  <code>200</code>
  <description>Request Queued.</description>
  <requestId>8059143026666797256</requestId>
  <messages>
    <message  msgId="8059143026666797257" description="Queued" />
  </messages>
</messageResponse>
{% endhighlight %}

### JSON

{% highlight voltMx %}{
  "messageResponse": {
    "requestId": "8059143026661134277",
    "description": "Request Queued. ",
    "code": 200,
    "messages": [
    {
      "description": "Queued",
      "msgId": 8059143026661134000
    } ]
  }
}
{% endhighlight %}

Response Status
---------------

  
| Code | Description |
| --- | --- |
| Status 200 | Request queued |
| Status 400 | Invalid request format |
| Status 401 | Unauthorized request |
| Status 500 | Server failure to process request |

<table class="TableStyle-RevisionTable" cellspacing="0" style="margin-left: 0;margin-right: auto;mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">7.1</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">AU</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">AU</td></tr></tbody></table>
