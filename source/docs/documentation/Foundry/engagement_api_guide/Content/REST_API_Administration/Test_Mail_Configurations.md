---
layout: "documentation"
category: "engagement_api_guide"
---
                            


Test Mail Configuration
=======================

The **Test Mail Configuration** API tests the mail configuration and ascertains, if the configuration is successful or not.

URL
---

The HTTP URL for the **Test Mail Configuration** API is:

{% highlight voltMx %}http://<<host>>:<<port>>/api/v1/mailconfig/test
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
| protocol |   | Yes | string | A protocol about a standard method used at each end of a communication channel. You must use a mail client to access a mail server. The mail client and mail server can exchange information with each other using a protocols.like SMTP/SMTPS |
| host |   | Yes | string | Host is like a store (a website) on a server so that it can be accessed over the Internet, for example: localhost |
| port |   | Yes | long | Port is an endpoint of communication. Port is always associated with an IP address of a host and the protocol type of the communication |
| defaultSenderId |   | Yes | string | Email ID of the sender |
| securityMode |   | Yes | string | The security protocols. For example, The Transport Layer Security (TLS) protocol, and Secure Sockets Layer (SSL) protocol |
| authRequired |   |   | boolean | If user authentication is required or not |
| authUser |   | Optional | string | Credentials to access the system |
| authPwd |   | Optional | string | Authentication password, It is in combination with authUser |
| supportedAttachmentFileTypes |   | Optional | String | Enter the attachment file types supported by the SMTP service provider. The file type must be separated by a comma. For example, pdf,doc,docx,xls,xlsx. By default, the types of attachments allowed are: .pdf, .xls, .xlsx, .csv, .txt, .doc, .docx, .ppt, .pptx, .pps, .zip, .rar, .tar, .gzip, .log, .jpeg, .jpg, .png. |
| maxSizeOfIndividualAttachmentInMB |   | Optional | double | This configuration restricts the max size of any attachment in the email. By default, the size of an attachment in the email should not exceed 10MB. |
| maxSizeOfAllAttachmentsInMB |   | Optional | double | This is the maximum size of the Email message including attachments and content (after base64 encoding), supported by your SMTP service provider. By default, the total size of attachments in the email should not exceed 10MB. |
| maxNumberOfAttachments |   | Optional | integer | This configuration restricts the max no. of attachments that can be sent in the email. By default, the maximum number of attachments that can be sent in an email is set to 4. |
| customProps |   |   |   | An array of custom properties |
|   | configKey | Optional | string | Key value pair |
|   | configValue | Optional | string | Key value pair |

Sample Request
--------------

{% highlight voltMx %}{
  "protocol": "SMTP/SMTPS",
  "host": "localhost",
  "port": "25",
  "defaultSenderId": "admin@voltmx.com",
  "securityMode": "TLS/SSL",
  "authRequired": "false",
  "authUser": "",
  "authPwd": "",
  "supportedAttachmentFileTypes": "pdf,xls,xlsx,csv,txt,doc,docx,ppt,pptx,pps,zip,rar,tar,gzip,log,jpeg,jpg,png",
  "maxSizeOfIndividualAttachmentInMB": 10.0,
  "maxSizeOfAllAttachmentsInMB": 10.0,
  "maxNumberOfAttachments": 4,
  "customProps": [
    {
      "configKey": "mail.smtp.ehlo",
      "configValue": "true"
    }
  ]
}
{% endhighlight %}

Sample Response
---------------

{% highlight voltMx %}

{

"message" : "Successfully connected to SMTP Server.",

"id" : ""

}


{% endhighlight %}

Response Status
---------------

  
| Code | Description |
| --- | --- |
| Status 200 | Successfully connected to SMTP server |
| Status 400 | Invalid request format |
| Status 401 | Unauthorized request |
| Status 500 | Server failure to process request |

<table class="TableStyle-RevisionTable" cellspacing="0" style="margin-left: 0;margin-right: auto;mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">7.1</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">AU</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">Au</td></tr></tbody></table>
