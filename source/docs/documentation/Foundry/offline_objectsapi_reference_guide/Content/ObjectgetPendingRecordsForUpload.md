---
layout: "documentation"
category: "offline_objectsapi_reference_guide"
---


\<object\>.getPendingRecordsForUpload
===================================

The **\<object\>.getPendingRecordsForUpload** API fetches the list of records that are yet to be uploaded.

> **Note:**  
*   This API is supported from V8 SP4 onwards.  
*   Supported for Windows from V8 SP4 Fix Pack 6 onwards.  
*   Supported for Mobile Web and Desktop Web channels from V8 SP4 Fix Pack 12 onwards.  
*   The column names and values provided as key value pairs are case sensitive.  

Volt MX  Iris (JavaScript)
-------------------------------

### Signature

{% highlight voltMx %}<object>.getPendingRecordsForUpload(options, onSuccessCallback, onFailureCallback)
{% endhighlight %}

### Parameters

  
| Parameter | Type | Description | Required |
| --- | --- | --- | --- |
| options | JSON | Reserved for future use, so the parameter is insignificant. But, the developer must pass some value such as null or { }. | Yes |
| onSuccessCallback | Function | The function is invoked when the pending records for upload are successfully fetched. | Yes |
| onFailureCallback | Function | The function is invoked when the pending records for upload are not successfully fetched. | Yes |

### Return Type

void

### Example

{% highlight voltMx %}var category = new voltmx.sdk.VMXObj("CATEGORY");

function successCallback(response) {
    //response holds the list of records which are yet to be uploaded.
    //response={"pendingSyncRecords": [{"UserId":123}]
    //}
}

function errorCallback(error) {
    voltmx.print("Failed to fetch pending records for uploads with error: " + JSON.stringify(error));
}
category.getPendingRecordsForUpload({}, successCallback, errorCallback);
{% endhighlight %}

Android (Java)
--------------

### Signature

{% highlight voltMx %}void <object>.getPendingRecordsForUpload(HashMap<String, Object> options, final VMXCallback syncCallback) throws Exception
{% endhighlight %}

### Parameters

  
| Parameter | Type | Description | Required |
| --- | --- | --- | --- |
| options | HashMap <String, Object> | Reserved for future use, so the parameter is insignificant. But, the developer must pass some value such as null or { }. | Yes |
| syncCallback | VMXCallback | The function is invoked when the pending records for upload are successfully fetched or on an error. | Yes |

### Return Type

void

### Example

{% highlight voltMx %}HashMap < String, Object > options = new HashMap < String, Object > ();
try {
    VMXObj category = new VMXObj("CATEGORY");
    category.getPendingRecordsForUpload(options, new VMXCallback() {
        @Override
        public void onSuccess(Object object) {
            Log.d("Pending records for upload", "Records are fetched
 successfully.");
        }
        @Override
        public void onFailure(object error) {
            OfflineObjectsException e = (OfflineObjectsException) error;
            Log.e("Pending records for upload ", "Fetching pending
 records for upload unsuccessful for category with Error :" + e.getMessage());
        }
    });
} catch (Exception e) {
    Log.e("Pending records for upload ", "Fetching pending
	records for upload unsuccessful for category with Error :" +
        e.getMessage());
}
{% endhighlight %}

iOS (Objective C)
-----------------

### Signature

{% highlight voltMx %}void <object> getPendingRecordsForUpload:(NSDictionary <NSString *, id> *)options 
		onSuccess:(VMXSuccessCompletionHandler)onSuccess 
		onFailure:(VMXFailureCompletionHandler)onFailure
{% endhighlight %}

### Parameters

  
| Parameter | Type | Description | Required |
| --- | --- | --- | --- |
| options | NSDictionary<NSString \*, id> | Reserved for future use, so the parameter is insignificant. But, the developer must pass some value such as null or { }. | Yes |
| onSuccess | VMXSuccessCompletionHandler | The function is invoked when the pending records for upload are successfully fetched. | Yes |
| onFailure | VMXFailureCompletionHandler | The function is invoked when the pending records for upload are not successfully fetched. | Yes |

### Return Type

void

### Example

{% highlight voltMx %}NSError * error;
VMXObj * category = [
    [VMXObj alloc] initWithName: @"CATEGORY"
    error: & error
];

if (!error) {
    [category getPendingRecordsForUpload: options
        onSuccess: ^ (id object) {
            NSLog(@"Records pending for upload fetched
		successfully.");
        }
        onFailure: ^ (id object) {
            OfflineObjectsError * error = (OfflineObjectsError) object;
            NSLog(@"Records pending for upload couldn’t be
		fetched with error %@", [error.userInfo localizedDescription]);
        }
    ];
} else {
    NSLog(@"VMXObj couldn’t be
	initialized with error %@", [error.userInfo localizedDescription]);
}
{% endhighlight %}
