---
layout: "documentation"
category: "iris_widget_prog_guide"
---
                                

You are here: Creating an Image Using a Constructor: voltmx.ui.Image2

Image Widget
============

Image widget is used to display a graphic image such as a company logo, photo, or illustration, in PNG, JPEG,WebP or GIF format, in an application.

Following are the key concepts in Image widget:

*   **Image as widget skin:** Image widget can be used to display an image as a background skin for a widget. For instance, a back button in a form can have an image depicting the back arrow as its skin.
    
*   **Image when failed and Image while downloading:** An image is displayed on a screen when the remote source is not available, or when the remote source is being downloaded.
    
*   **Company logo:** Image widget is used to display the company logo in a form.
    
*   **Profile picture:** Image widget is used to set the profile picture of a user in an application. The shape of an image can also be changed using the [clipView](Image_Properties.html#clipView) property. For instance, consider the following screen that displays the profile picture of an employee in a circular view.
    
*   **Base 64:** When you get base 64 strings from the backend, the image widget is used to display it as an image in an application. For example, in the following employee list screen, the employee images are displayed using the base 64 strings from the backend.
    

Widgets are normally added to your application using Volt MX Iris, but can also be added from code. For general information on using widgets in Volt MX Iris, see [Designing an Application]({{ site.baseurl }}/docs/documentation/Iris/iris_user_guide/Content/Part_II_CreatingAnApplication.html) in the [Iris User Guide]({{ site.baseurl }}/docs/documentation/Iris/iris_user_guide/Content/Introduction.html).

For general information on the Image2 widget see the []({{ site.baseurl }}/docs/documentation/Iris/iris_user_guide/Content/Button.html)[Image2]({{ site.baseurl }}/docs/documentation/Iris/iris_user_guide/Content/Image2.html) topic in the Volt MX Iris User Guide.

This widget supports drag and drop of images for iOS 11 on iPad.

The Image widget capabilities can be broadly categorized into the following:

*   [Layout](#layout)
*   [Animations](#animations)
*   [Data Management](#data-management)
*   [User Input Handling](#user-input-handling)
*   [3D Touch](#3d-touch)
*   [UI Appearance](#ui-appearance)
*   [Enabling RTL](#enabling-rtl)
*   [Miscellaneous](#miscellaneous)
*   [Configurations Common To All Widgets](#configurations-common-to-all-widgets)

#### Layout

  
| Events | Description |
| --- | --- |
| [doLayout](Image_Events.html#doLayout) | This event is invoked for every widget when the widget position and dimensions are computed. |

 

| Properties | Description |
| --- | --- |
| [anchorPoint](Image_Properties.html#anchorPo) | Specifies the anchor point of the widget bounds rectangle using the widget's coordinate space. |
| [bottom](Image_Properties.html#bottom) | Determines the bottom edge of the widget and is measured from the bottom bounds of the parent container. |
| [centerX](Image_Properties.html#centerX) | Determines the center of a widget measured from the left bounds of the parent container. |
| [centerY](Image_Properties.html#centerY) | Determines the center of a widget measured from the top bounds of the parent container. |
| [left](Image_Properties.html#left) | Determines the lower left corner edge of the widget and is measured from the left bounds of the parent container. |
| [margin](Image_Properties.html#margin) | Defines the space around a widget. |
| [marginInPixel](Image_Properties.html#marginIn) | Indicates if the margin is to be applied in pixels or in percentage. |
| [maxHeight](Image_Properties.html#maxHeigh) | Specifies the maximum height of the widget and is applicable only when the height property is not specified. |
| [maxWidth](Image_Properties.html#maxWidth) | Specifies the maximum width of the widget and is applicable only when the width property is not specified. |
| [minHeight](Image_Properties.html#minHeigh) | Specifies the minimum height of the widget and is applicable only when the height property is not specified. |
| [minWidth](Image_Properties.html#minWidth) | Specifies the minimum width of the widget and is applicable only when the width property is not specified. |
| [padding](Image_Properties.html#padding) | Defines the space between the content of the widget and the widget boundaries. |
| [paddingInPixel](Image_Properties.html#paddingInPixel) | Indicates if the padding is to be applied in pixels or in percentage. |
| [referenceHeight](Image_Properties.html#referenceHeight) | The reference image height in pixels. |
| [referenceWidth](Image_Properties.html#referenceWidth) | The reference image width in pixels. |
| [top](Image_Properties.html#top) | Determines the top edge of the widget and measured from the top bounds of the parent container. |
| [width](Image_Properties.html#width) | Determines the width of the widget and is measured along the x-axis. |
| [zIndex](Image_Properties.html#zIndex) | Specifies the stack order of a widget. |

  

#### Animations

| Methods | Description |
| --- | --- |
| [animate](Image_Method.html#animate) | Applies an animation to the widget. |

 

| Properties | Description |
| --- | --- |
| [transform](Image_Properties.html#transfor) | Contains an animation transformation that can be used to animate the widget. |
| [widgetSwipeMove](Image_Properties.html#widgetSwipeMove) | Used to enable and configure the left or right swipe actions for a widget. |

 

#### Data Management

| Methods | Description |
| --- | --- |
| [addOverlayWidgets]({{ site.baseurl }}/docs/documentation/Iris/iris_widget_prog_guide/Content/Image_Method.html#addOverlayWidgets) | Takes an array of widgets as input, which are to be added as overlay widgets on the Image widget. |
| [removeOverlayWidgets]({{ site.baseurl }}/docs/documentation/Iris/iris_widget_prog_guide/Content/Image_Method.html#removeOverlayWidgets) | Takes an array of widget references as input, which are to be removed as overlay widgets from an Image widget |
| [clone](Image_Method.html#clone) | When this method is used on a container widget, then all the widgets inside the container are cloned. |

 

| Properties | Description |
| --- | --- |
| [cacheConfig](Image_Properties.html#cacheConfig) | Used to configure the cachePolicy and storagePolicy of the cache responses. |
| [src](Image_Properties.html#src) | Specifies the source of the image to be displayed. |

 

#### 3D Touch

| Methods | Description |
| --- | --- |
| [registerForPeekandPop](Image_Method.html#register) | Registers a widget to enable 3D Touch peek and pop gestures. |
| [setOnPeek](Image_Method.html#setOnPek) | Sets and overrides the existing onPeekCallback for the widget. |
| [setOnPop](Image_Method.html#setOnPop) | Overrides the existing onPopCallback for the widget. |
| [unregisterForPeekandPop](Image_Method.html#unregist) | Unregisters a widget from 3D Touch peek and pop gestures. |

 

#### User Input Handling

| Events | Description |
| --- | --- |
| [onScrollWidgetPosition](Image_Events.html#onScrollWidgetPosition) | An event callback is invoked by the platform when the widget location position gets changed on scrolling. |
| [onTouchEnd](Image_Events.html#onTouchEnd) | An event callback is invoked by the platform when the user touch is released from the touch surface. |
| [onTouchMove](Image_Events.html#onTouchMove) | An event callback is invoked by the platform when the touch moves on the touch surface continuously until movement ends. |
| [onTouchStart](Image_Events.html#onTouchStart) | An event callback is invoked by the platform when the user touches the touch surface. |

 

| Methods | Description |
| --- | --- |
| [addGestureRecognizer](Image_Method.html#addGestureRecognizer) | Allows you to set a gesture recognizer for a specified gesture for a specified widget. |
| [removeGestureRecognizer](Image_Method.html#removeGestureRecognizer) | Allows you to remove the specified gesture recognizer for the specified widget. |
| [setGestureRecognizer](Image_Method.html#setGestureRecognizer) | Allows you to set a gesture recognizer for a specified gesture for a specified widget. |

| Properties | Description |
| --- | --- |
| [zoomEnabled]({{ site.baseurl }}/docs/documentation/Iris/iris_widget_prog_guide/Content/Image_Properties.html#zoomEnabled) | This is a Boolean property that enables zooming capabilities for an Image widget. |
| [zoomValue]({{ site.baseurl }}/docs/documentation/Iris/iris_widget_prog_guide/Content/Image_Properties.html#zoomValue) | This is a Float-value property that defines the current zoom state of an Image widget. |

#### UI Appearance

| Properties | Description |
| --- | --- |
| [blur](Image_Properties.html#blur) | You can enable or disable a blur-effect for a widget |
| [clipView](Image_Properties.html#clipView) | Defines a shape to clip the widget view. |
| [containerWeight](Image_Properties.html#containerWeight) | Specifies percentage of weight to be allocated by its parent widget. |
| [glossyEffect](Image_Properties.html#glossyEffect) | Specifies a glossy effect on an image. |
| [hoverSkin](Image_Properties.html#hoverSkin) | Specifies the look and feel of a widget when the cursor hovers on the widget. |
| [imageScaleMode](Image_Properties.html#imageScaleMode) | Specifies how the rendered image's width and height are identified when those of the source image varies from the Image widget itself. |
| [opacity](Image_Properties.html#opacity) | Specifies the opacity of the widget. |
| [padding](Image_Properties.html#padding) | Defines the space between the content of the widget and the widget boundaries. |
| [paddingInPixel](Image_Properties.html#paddingI) | Indicates if the padding is to be applied in pixels or in percentage. |
| [renderAsAnchor](Image_Properties.html#renderAs) | To offer an acceptable user experience, one of the image in a segment is made clickable and the onClick event for the segment is bound to a image. |
| [shadowDepth](Image_Properties.html#shadowDepth) | Defines the depth of the shadow effect applied to the Image Widget. |
| [skin](Image_Properties.html#skin) | Specifies the look and feel of the Image. |
| [widgetAlignment](Image_Properties.html#widgetAlignment) | Indicates how a widget is to be anchored with respect to its parent. |
| [tintConfig](Image_Properties.html#tintConfig) | Sets the tint color and tint mode of the widget. |

 

| Methods | Description |
| --- | --- |
| [getImageAsRawBytes](Image_Method.html#ImgRaw) | Retrieves the image as rawbytes. |
| [getImageHeight](Image_Method.html#ImgHeight) | Retrieves the image height as an integer. |
| [getImageWidth](Image_Method.html#ImgWidth) | Retrieves the image width as an integer. |

#### Enabling RTL

| Properties | Description |
| --- | --- |
| [retainContentAlignment](Image_Properties.html#retainContentAlignment) | Helps to retain the content alignment of the widget while applying RTL. |
| [retainFlexPositionProperties](Image_Properties.html#retainFlexPositionProperties) | Helps to retain the left, right and padding properties while applying RTL. |
| [retainFlowHorizontalAlignment](Image_Properties.html#retainFlowHorizontalAlignment) | Enables you to change the horizontal flow of the widget from left to right. |

#### Miscellaneous

| Properties | Description |
| --- | --- |
| [base64](Image_Properties.html#base64) | Returns the base64 encoded string of the image raw bytes. |
| [cursorType](Image_Properties.html#cursorType) | Specifies the type of the mouse pointer used. |
| [rawBytes](Image_Properties.html#rawBytes) | Represents the images raw bytes. |

 

| Methods | Description |
| --- | --- |
| [getBadge](Image_Method.html#getBadge) | Enables you to read the badge value (if any) attached to the specified widget. |
| [scale](Image_Method.html#scale) | Scales the bitmap in the current Image widget to a larger or smaller size. |
| [setBadge](Image_Method.html#setBadge) | Enables you to set the badge value to the given widget at the upper, right corner of the widget. |

 

| Events | Description |
| --- | --- |
| [onDownloadComplete](Image_Events.html#onDownlo) | Triggered when the image download from the URL is complete. |

 

#### Configurations Common To All Widgets

| Methods | Description |
| --- | --- |
| [blur](Image_Properties.html#blur) | Enables you to make the widget look unfocused. |
| [convertPointFromWidget](Image_Method.html#convertPointFromWidget) | Allows you to convert the coordinate system from a widget to a point (receiver's coordinate system). |
| [convertPointToWidget](Image_Method.html#convertPointToWidget) | Allows you to convert the coordinate system from a point (receiver's coordinate system) to a widget. |
| [removeFromParent](Image_Method.html#removeFromParent) | Allows you to remove a child widget from a parent widget. |
| [setEnabled](Image_Method.html#setEnabled) | Specifies the widget that must be enabled or disabled. |
| [setFocus](Image_Method.html#setFocus) | Specifies the widget on which there must be focus. |
| [setVisibility](Image_Method.html#setVisibility) | Sets the visibility of the widget. |

 

| Properties | Description |
| --- | --- |
| [accessibilityConfig](Image_Properties.html#accessibilityConfig) | Enables you to control accessibility behavior and alternative text for the widget. |
| [enable](Image_Properties.html#enable) | Allows you to make a widget visible but not actionable. |
| [enableCache](Image_Properties.html#enableCa) | Enables you to improve the performance of Positional Dimension Animations. |
| [id](Image_Properties.html#id) | id is a unique identifier of Image consisting of alpha numeric characters. |
| [info](Image_Properties.html#info) | A custom JSObject with the key value pairs that a developer can use to store the context with the widget. |
| [isVisible](Image_Properties.html#isVisible) | Controls the visibility of a widget on the Form. |
| [parent](Image_Properties.html#parent) | Helps you access the parent of the widget. |

Image Widget Basics
-------------------

### Creating an Image Using a Constructor: voltmx.ui.Image2

{% highlight voltMx %}
var myimage = new voltmx.ui.Image2 (basicConf, layoutConf, pspConf);
{% endhighlight %}

*   **basicConf** is an object with basic properties.
*   **layoutConf** is an object with layout properties.
*   **pspConf** is an object with platform specific properties.

> **_Note:_** The configuration properties should be passed only in the respective configuration objects otherwise they are ignored.

Example

{% highlight voltMx %}//Creating the Image with isVisible:true.
var basicConfImage = {
    id: "imageIdTest",
    isVisible: true,
    src: "http://www.fordesigner.com/imguploads/Image/cjbc/zcool/png20080525/1211728825.png",
    imageWhenFailed: "rn_icon1.png",
    imageWhileDownloading: "new.png"
};

var layoutConfImage = {
    containerWeight: 100
};

var PSPConfImage = {
    glossyEffect: constants.MAGE_GLOSSY_EFFECT_RADIAL
};

var imageIdTest = new voltmx.ui.Image2(basicConfImage, layoutConfImage, PSPConfImage);

//Reading the visibility of the Image
alert("Image visibility is ::" + imageIdTest.isVisible);
{% endhighlight %}

For backward compatibility with support for all deprecated properties and behaviors, use the constructor **voltmx.ui.Image**.

{% highlight voltMx %}
var Image1 = new voltmx.ui.Image(basicConf, layoutConf, pspConf)
{% endhighlight %}

### Customizing Appearance

You can customize the appearance of the Image widget using the following properties:

*   widgetAlignment: Specifies the alignment of the widget.
*   margin: Defines the space around a widget.
*   padding: Defines the space between the content of the widget and the widget boundaries.

### Naming Conventions

To specify a local image, you must add the image file to the _resources_ folder of the Application.

> **_Note:_** For more information on how to add these files, see the _Working with Resources_ section of the _VoltMX Iris User Guide_.

The image can be either a bitmap or a vector graphics file.

Image files can be of GIF, animated GIF, JPG, PNG, or WebP formats.

Vector graphics are also supported for the following formats on the following platforms:

*   Android supports .xml files
*   iOS supports .pdf files
*   SPA supports .svg files
*   Windows (Creators Edition) supports .svg files.

The files that you add must follow a particular naming convention. The following is the naming convention that you must follow:

*   The file name must contain only lowercase characters.
*   The file name must start only with an alphabet.
*   The file name can contain numbers.
*   Do not use any reserved words or keywords ( of JavaScript) as the file names for the images.

*   Numerical characters.

The following table shows a few examples of valid and invalid file names for the images:

| Valid File Names | Invalid File Names | Remarks |
| --- | --- | --- |
| myicon.PNG | Myicon.png | The file name is invalid because it contains uppercase character. |
| icon2.PNG | Icon\_2.png | The file name is invalid because it contains uppercase character and an underscore. |
| accntsummary.PNG | aCCNT&summary.PNG | The file name is invalid because it contains uppercase characters and special character |
| accountdetails.png | Details.PNG | The file name is invalid because it contains uppercase character. |
| flightstatus123.png | continue.PNG | The file name contains a Java keyword. |

> **_Note:_** Volt MX Iris does not recognize images that have invalid file names.

### Image Caching

Image caching is a feature in Volt MX Iris V8 that ensures that the Image Widget can use URLs as a source for an image. This feature is designed to use the same URL multiple times in an application to load the image as fast as possible with minimal server sync delay.

To configure Image Caching, do the following:

1.  On your machine where Volt MX Iris is installed, navigate to Volt MX Iris project folder: _<WorkspaceName>\\<ProjectName>\\resources\\common_.
2.  Open the **infoplist\_configuration.json** file.
3.  Towards the end of the file, add the following content:{% highlight voltMx %}{
    “imageWidgetURLCache”:
    	{
    	“cacheSize”:10,
    		// Value should greater than equal to 0
    		// 0 for max memory 
    	“skipServerValidation”:YES
    		//YES for once cached no need to sync with server again to check the updated resource
    	//NO for Sync with the server to check for the updated resource.
    	}  
    }
    
    {% endhighlight %}
4.  Save and close the file.  
    Image caching is enabled in the Volt MX cache mechanism.

