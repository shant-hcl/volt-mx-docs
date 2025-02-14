---
layout: "documentation"
category: "engagement_api_guide"
---
                            


Get File Upload Status by ID
============================

The **Get File Upload Status by ID** API accepts the upload ID as an input parameter and fetches the current status details such as success or bad data.This upload is returned by the engagement server when the file upload is initiated by invoking the upload API.

URL
---

The HTTP URL for Get File Upload Status by ID API is:

{% highlight voltMx %}http://<<host>>:<<port>>/api/v1/batchinfo/status/{id}
{% endhighlight %}

Method
------

GET

Sample Responses
----------------

### Bulk Geolocation

#### Upload Status Code 0 (In Progress)

{% highlight voltMx %}{ "dataType" : "GEO_LOCATIONS", 
                "uploadStatusCode":0,
                "statusMessage" : "Processing initialized", 
                "importedDate" : "09/20/2016 01:29:08 PM GMT", 
                "importedBy" : "admin", 
                "id" : "73666813857345684569"
}
{% endhighlight %}

#### Upload Status Code 200 (Completed)

{% highlight voltMx %}{ "dataType" : "GEO_LOCATIONS", 
                "uploadStatusCode":200,
                "statusMessage" : "Successfully imported all the locations", 
                "importedDate" : "09/20/2016 01:29:08 PM GMT", 
                "importedBy" : "admin", 
                "id" : "73666813857345684569"
}

{% endhighlight %}

#### Upload Status Code 400 (Missing or invalid data for one or more records)

{% highlight voltMx %}{ "dataType" : "GEO_LOCATIONS", 
			"uploadStatusCode":400,
			"statusMessage" : "Uploaded file has got errors", 
			"importedDate" : "09/20/2016 01:29:08 PM GMT", 
			"importedBy" : "admin", 
			"id" : "73666813857345684569"
}

{% endhighlight %}

#### Upload Status Code 500 (Invalid Headers)

{% highlight voltMx %}{ "dataType" : "GEO_LOCATIONS", 
                "uploadStatusCode":500,
                "statusMessage" : "Invalid header value xxxx provided.", 
                "importedDate" : "09/20/2016 01:29:08 PM GMT", 
                "importedBy" : "admin", 
                "id" : "73666813857345684569"
}
{% endhighlight %}

### Import Users

#### Upload Status Code 0 (In Progress)

{% highlight voltMx %}{ "dataType" : "AUDIENCE_MEMBERS", 
                "uploadStatusCode":0,
                "statusMessage" : "Processing initialized", 
                "importedDate" : "09/20/2016 01:29:08 PM GMT", 
                "importedBy" : "admin", 
                "id" : "73666813857345684569"
}
{% endhighlight %}

#### Upload Status Code 200 (Completed)

{% highlight voltMx %}{ "dataType" : "AUDIENCE_MEMBERS", 
                "uploadStatusCode":200,
                "statusMessage" : "Successfully uploaded requests of count : 100", 
                "importedDate" : "09/20/2016 01:29:08 PM GMT", 
                "importedBy" : "admin", 
                "id" : "73666813857345684569"
}
{% endhighlight %}

#### Upload Status Code 400 (File has invalid data for one or more users)

{% highlight voltMx %}{ "dataType" : "AUDIENCE_MEMBERS", 
			"uploadStatusCode":400,
			"statusMessage" : "Uploaded file has got errors", 
			"importedDate" : "09/20/2016 01:29:08 PM GMT", 
			"importedBy" : "admin", 
			"id" : "73666813857345684569"
}
{% endhighlight %}

#### Upload Status Code 500 (Invalid Headers)

{% highlight voltMx %}{ "dataType" : "AUDIENCE_MEMBERS", 
                "uploadStatusCode":500,
                "statusMessage" : "Header containing user attribute list is missing or few of the required attributes are missing in the uploaded file. Also, check if the file delimiter and selected delimiter type are matching", 
                "importedDate" : "09/20/2016 01:29:08 PM GMT", 
                "importedBy" : "admin", 
                "id" : "73666813857345684569"
}
{% endhighlight %}

#### Upload Status Code 500 (Processing failed)

{% highlight voltMx %}            
            { "dataType" : "AUDIENCE_MEMBERS", 
                "uploadStatusCode":500,
                "statusMessage" : "Failed to upload audience members", 
                "importedDate" : "09/20/2016 01:29:08 PM GMT", 
                "importedBy" : "admin", 
                "id" : "73666813857345684569"
}
{% endhighlight %}

### Bulk Push

#### Upload Status Code 0 (In Progress)

{% highlight voltMx %}{
	"dataType": "BULK_PUSH",
	"statusMessage": "Processing Initialized",
	"importedDate": "09/20/2016 12:56:46 PM GMT",
	"importedBy": "bvuser@voltmx.com",
	"uploadStatusCode": 0,
	"id": "7366557095490382404"
}
{% endhighlight %}

#### Upload Status Code 200 (Processing successful)

{% highlight voltMx %}{
	"dataType": "BULK_PUSH",
	"statusMessage": "Messages processed successfully",
	"importedDate": "03/15/2018 03:25:32 PM IST",
	"importedBy": "xxx@yyy.com",
	"requestId": 8825493127599914874,
	"uploadStatusCode": 200,
	"id": "8825493117394875342"
}
{% endhighlight %}

#### Upload Status Code 400 (Invalid users)

{% highlight voltMx %}            
            {
  "dataType": "BULK_PUSH",
  "statusMessage": "Invalid subscribers",
  "importedDate": "09/20/2016 01:31:20 PM GMT",
  "importedBy": "bvuser@voltmx.com",
  "uploadStatusCode": 400,
  "id": "7366689869640468247"
}

{% endhighlight %}

#### Upload Status code 400 (Invalid users)

{% highlight voltMx %}
{
  "dataType" : "BULK_PUSH",
  "statusMessage" : "Queued sucessfully, but contains invalid subscribers.",
  "importedDate" : "09/20/2016 12:38:55 PM GMT",
  "importedBy" : "bvuser@voltmx.com",
  "uploadStatusCode": 400,
  "id" : "7366488585436004154"
}

{% endhighlight %}

#### Upload Status Code 500 (Invalid format)

{% highlight voltMx %}{
  "dataType": "BULK_PUSH",
  "statusMessage": "Line 15, Invalid values",
  "importedDate": "09/20/2016 01:31:20 PM GMT",
  "importedBy": "bvuser@voltmx.com",
  "uploadStatusCode": 500,
  "id": "7366689869640468247"
}

{% endhighlight %}

Response Status
---------------

  
| Code | Description |
| --- | --- |
| Status 200 | Messages queued sucessfullyProcessing initialized |
| Status 400 | Invalid ID provided |
| Status 401 | Unauthorized request |
| Status 500 | Server failure to process request. |

<table class="TableStyle-RevisionTable" cellspacing="0" style="mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">7.1</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">AU</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">AU</td></tr></tbody></table>
