---
layout: "documentation"
category: "engagement_api_guide"
---
                            


Get SMS Templates by Pagination
===============================

The **Get SMS Templates by Pagination** API accepts start and pageSize as input parameters and returns all the SMS template details. The pageSize represents the maximum number of the SMS templates for which the details are to be returned. If the start is specified, the number of the SMS templates that are returned are from start position to pageSize value. For example: if the start is zero and pageSize is five, then six SMS templates from position zero to five are returned.

> **_Note:_** This API will return SMS Template details for both Text as well as Voice SMS.

URL
---

The HTTP URL for **Get SMS Templates by Pagination** API is:

{% highlight voltMx %}http://<host>:<port>/api/v1/templates/smstemplates?start=0&pageSize=10
{% endhighlight %}

Method
------

GET

Output Parameters
-----------------

The following fields are output parameters:

  
| Output Parameter | Level – Two | Type | Description |
| --- | --- | --- | --- |
| total |   | long | Total number of SMS templates |
| smsTemplates |   |   | An array of smsTemplates objects |
|   | id | long | Unique ID assigned to the SMS template |
|   | templateName | string | SMS template name |
|   | template | string | SMS template details |
|   | lastModifiedBy | string | A user name that shows who last modified the SMS template |
|   | lastModifiedDateStr | string | Date on which the SMS template was last modified |
|   | createdDateStr | string | Date on which the SMS template is created |
|   | createdBy | string | A user name that shows who created the SMS template |

Sample Response
---------------

{% highlight voltMx %}{
  "total" : 3,
  "smsTemplates" : [ {
    "id" : 1,
    "templateName" : "eBay summer sale 2016",
    "template" : "##First Name####Last Name##",
    "lastModifiedBy" : "admin",
    "lastModifiedDateStr" : "06/29/2016 04:29:09 PM IST",
    "createdDateStr" : "06/29/2016 04:29:09 PM IST",
    "createdBy" : "admin"
  }, {
    "id" : 2,
    "templateName" : "Flipkart shopping sale",
    "template" : "##Email##",
    "lastModifiedBy" : "admin",
    "lastModifiedDateStr" : "06/29/2016 04:29:21 PM IST",
    "createdDateStr" : "06/29/2016 04:29:21 PM IST",
    "createdBy" : "admin"
  }, {
    "id" : 3,
    "templateName" : "Amazon online books sale",
    "template" : "##Mobile Number####First Name##",
    "lastModifiedBy" : "admin",
    "lastModifiedDateStr" : "06/29/2016 04:29:36 PM IST",
    "createdDateStr" : "06/29/2016 04:29:36 PM IST",
    "createdBy" : "admin"
  } ]
}
{% endhighlight %}

Response Status
---------------

  
| Code | Description |
| --- | --- |
| Status 200 | Array of SMS templates |
| Status 400 | No mail templates found |
| Status 500 | Server failure to process request |

<table class="TableStyle-RevisionTable" cellspacing="0" style="margin-left: 0;margin-right: auto;mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">7.1</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">AU</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">AU</td></tr></tbody></table>
