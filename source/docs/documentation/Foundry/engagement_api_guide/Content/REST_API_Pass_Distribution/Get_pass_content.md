---
layout: "documentation"
category: "engagement_api_guide"
---
                            


Get Pass Content
================

The **Get Pass Content** API accepts the pass ID as an input parameter and fetches the pass content details.

URL
---

The HTTP URL for **Get Pass Content** API is:

{% highlight voltMx %}http://<<host>>:<<port>>/api/v1/pass/<<passid>>/content
{% endhighlight %}

Method
------

GET

Output Parameters
-----------------

The following fields are output parameters:

  
| Output Parameter | Level – Two | Description |
| --- | --- | --- |
| passContent |   | An array of passContent objects |
|   | basicDetails | An array of basicDetails objects. For more details, [see](Pass_Distribution_main.html#passtemplates) |
|   | appearance | An array of appearance objects. For more details, [see](Pass_Distribution_main.html#appearance_for_dist) |
|   | frontLayout | An array of frontLayout objects. For more details, [see](Pass_Distribution_main.html#frontLayout_for_dist) |
|   | backLayout | An array of backLayout objects. For more details, [see](Pass_Distribution_main.html#backLayout_for_dist) |
|   | passRelevance | An array of passRelevance objects. For more details, [see](Pass_Distribution_main.html#passRelevance_for_dist) |
|   | passRules | An array of passRules objects. For more details, [see](Pass_Distribution_main.html#passRules_for_dist) |
|   | languageDetails | An array of languageDetails objects. For more details, [see](Pass_Distribution_main.html#languageDetails_for_dist) |

Sample Response
---------------

{% highlight voltMx %}{
  "passContent": {
    "basicDetails": {
      "passType": "BOARDING",
      "passTypeIdentifier": "pass.com.VoltMX Foundry Messaging.pass1",
      "passSerialNumberType": "AUTO_GEN",
      "passSerialNumber": "3988395953726884337",
      "groupIdentifier": "",
      "appLaunchURL": "",
      "ituneIdentifiers": "",
      "eventTicketType": "",
      "webServiceUrl": "http://localhost:8080/VoltMX Foundry Messaging/",
      "customJsonData": "",
      "timezone": "GMT-05:00",
      "organizationName": "VoltMX",
      "description": "VoltMX"
    },
    "appearance": {
      "bgColor": "#64798c",
      "labelColor": "#ccdae9",
      "valueColor": "#ffffff",
      "suppressStripShine": false,
      "images": [
        {
          "imageType": "LOGO",
          "url": "http://icons.iconarchive.com/icons/wineass/ios7-redesign/512/Sample-icon.png",
          "blob": false,
          "imageId": "",
          "size": 8352,
          "extension": "png"
        },
        {
          "imageType": "ICON",
          "url": "http://icons.iconarchive.com/icons/wineass/ios7-redesign/512/Sample-icon.png",
          "blob": false,
          "imageId": "",
          "size": 8352,
          "extension": "png"
        },
        {
          "imageType": "FOOTER",
          "url": "http://icons.iconarchive.com/icons/wineass/ios7-redesign/512/Sample-icon.png",
          "blob": false,
          "imageId": "",
          "size": 8352,
          "extension": "png"
        }
      ]
    },
    "frontLayout": {
      "logoText": "LT",
      "transitType": "AIR",
      "headerFields": [
        {
          "label": "HFL1",
          "data": "HFD1",
          "dataType": "TEXT",
          "numberFormat": "",
          "currency": "",
          "dateTimeFormat": "",
          "displayRelatively": false,
          "ignoreTimezone": false,
          "alignment": "LEFT",
          "autolink": [
            
          ],
          "key": "HFN1"
        }
      ],
      "primaryFields": [
        
      ],
      "auxiliaryFields": [
        
      ],
      "secondaryFields": [
        
      ],
      "barcodeDetails": {
        "barcodeType": "PDF417",
        "embeddedMessageType": "PASS_SERIAL_NO",
        "message": "3988395953726884337",
        "alternativeTextType": "BARCODE_CONTENTS",
        "alternateText": "3988395953726884337",
        "embeddedFormat": "UTF_8"
      }
    },
    "backLayout": {
      "fields": [
        {
          "label": "BFL1",
          "data": "BFV1",
          "dataType": "TEXT",
          "numberFormat": "",
          "currency": "",
          "dateTimeFormat": "",
          "displayRelatively": false,
          "ignoreTimezone": false,
          "alignment": "LEFT",
          "autolink": [
            
          ],
          "key": "BFN1"
        }
      ]
    },
    "passRelevance": {
      "relevantDate": "",
      "ignoreTimezone": false,
      "relevantLocations": [
        
      ],
      "relevantBeacons": [
        
      ],
      "maxDistance": ""
    },
    "passRules": {
      "dateRestriction": "PERMANENTLY_AVAILABLE",
      "stopAfter": "",
      "expiryDate": "",
      "voided": false
    },
    "languageDetails": {
      "originalFields": [
        
      ],
      "languageEntries": "",
      "passLanguage": "EN"
    }
  }
}
{% endhighlight %}

Response Status
---------------

  
| Code | Description |
| --- | --- |
| Status 200 | Array of pass content details |
| Status 401 | Unauthorized request |
| Status 500 | Server failure to process request |

<table class="TableStyle-RevisionTable" cellspacing="0" style="margin-left: 0;margin-right: auto;mc-table-style: url('../Resources/TableStyles/RevisionTable.css');" data-mc-conditions="Default.HTML"><colgroup><col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"> <col class="TableStyle-RevisionTable-Column-Column1"></colgroup><tbody><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Rev</td><td class="TableStyle-RevisionTable-BodyE-Column1-Body1">Author</td><td class="TableStyle-RevisionTable-BodyD-Column1-Body1">Edits</td></tr><tr class="TableStyle-RevisionTable-Body-Body1"><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">7.1</td><td class="TableStyle-RevisionTable-BodyB-Column1-Body1">AU</td><td class="TableStyle-RevisionTable-BodyA-Column1-Body1">AU</td></tr></tbody></table>
