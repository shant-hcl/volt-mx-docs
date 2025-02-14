---
layout: "documentation"
category: "offline_objects_releasenotes"
---
                            

[![](Resources/Images/pdf.png)](http://docs.voltmx.com/7_x_PDFs/mobilefoundry/offline_objects_releasenotes.pdf "VoltMX Offline Objects Release Notes")

Offline Objects Release Notes: Known Issues

Known Issues (Beta)
===================

<table style="width: 100%;margin-left: 0;margin-right: auto;mc-table-style: url('Resources/TableStyles/Basic.css');" class="TableStyle-Basic" cellspacing="0"><colgroup><col class="TableStyle-Basic-Column-Column1"></colgroup><tbody><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">Offline Objects feature implements a get method that uses OData filter to fetch data. The OData filter may not be supported by all back-ends. Currently, this only supports RDBMS, Salesforce, and SAP back-ends.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">Client Side Sync fails when primary key is Numeric DataType in the Foundry console.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">VoltMXsdk object does not initialize when there is no data network. On offline objects, methods (Setup/CRUD)can not be called.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">When sync is initiated without invoking the Setup API, an error message is displayed. This error message is not comprehensible.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">The boolean data type is numeric for Android and iOS. This is incorrect. The boolean data type must be boolean.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">An app developed using Volt MX Iris along with Offline Objects will not launch on Xcode 8.0.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">Attribute of datatype date is not validated against the date format. This needs to be validated against the date format.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">Native bindings API artifacts (zip files) are not importing into existing apps. They are imported only when existing apps are reopened. There is no problem with new apps. The native bindings API artifacts comes from Foundry SDK plugin.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">When the <b>softdeletefield</b> is not specified in the service definition (<b>service-def</b>)file, a null pointer exception appears.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">An app developer must pass all the fields of a record during the update. Currently, a partial update of a record is not supported. If data is not passed to a field then a null value will be inserted for the value of such fields.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyD-Column1-Body1">For Offline Objects, in the beta version, the log level by default is <b>info</b>. The log level is set to info for better debugging capability. The end user will not be able to change the log level.</td></tr><tr class="TableStyle-Basic-Body-Body1"><td class="TableStyle-Basic-BodyA-Column1-Body1">Network availability is a must during Offline objects setup. For setup failures, offline objects framework does not display relevant error messages.</td></tr></tbody></table>

[Open topic with navigation](../Content/Known_Issues.html)

Comments

[Reply](#)

 

</div> <input class="comment-submit" type="button" value="Submit" > </div> </div> </body> <.html></x-turndown>
