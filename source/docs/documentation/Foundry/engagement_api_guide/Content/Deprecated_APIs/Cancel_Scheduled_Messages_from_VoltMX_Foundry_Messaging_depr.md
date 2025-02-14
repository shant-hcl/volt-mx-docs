---
layout: "documentation"
category: "engagement_api_guide"
---
                            


Cancel Scheduled Messages from Volt MX Foundry Engagement Services
=================================================================

The **Cancel Scheduled Messages from Volt MX Foundry Engagement Services** API is used to cancel the scheduled messages from Volt MX Foundry Engagement Services.

> **_Note:_** The Cancel Scheduled Messages from Volt MX Foundry Engagement Services API is maintained here to preserve backward compatibility.  
We encourage you to use :  
[Cancel Scheduled Messages from Volt MX Foundry Engagement Services API](../Push_Message_APIs/Cancel_Scheduled_Messages_from_VoltMX_Foundry_Messaging.html)

URL
---

The HTTP URL for Cancel Scheduled Messages from Volt MX Foundry Engagement Services API is:

{% highlight voltMx %}http://<host or ip>:<port>/service/entrydata/cancelmessage/$requestID
{% endhighlight %}

Method
------

HTTP GET / HTTP POST

Input Parameters
----------------

  
| Input Parameter | Type | Description |
| --- | --- | --- |
| Request ID | String | Request ID is appended at the end of the URL. Use the Request ID which was generated as part of push message response. |

Response Status
---------------

  
| Code | Description |
| --- | --- |
| 200 | Cancelled ${no. of messages} message entries of the message with ID : ${requestID} |
| 400 | Invalid request ID |
| 400 | No cancellable messages found |

<table class="TableStyle-RevisionTable" cellspacing="0" style="margin-left: 0;margin-right: auto;mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">7.1</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">AU</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">AU</td></tr></tbody></table>
