jQuery Google Analytics Tracker by Izilla Search & Display 
==========================================================

### A complete Google Analytics jQuery plugin with cross-domain, external link events and file download tracking 

This Google Analytics jQuery plugin is designed to extend the standard Google Analytics Tracking Tag with a minimum amount of website modification. 

**The primary features are:**

1. Allows cross-domain tracking by passing the session information to domains other than your primary domain. This is useful when you have another domain for your shopping cart or payment gateway.

2. Allows for multiple tracking tags (Property IDs) on one website. This is handy when using an additional property ID for tracking multiple enterprise domains, or when using third party web applications to deliver certain functionality to your website visitors.

3. Allows the tracking of file downloads as page views in your reporting. No modification to your links required. This allows you to specify the file types you want to track as a page view. Links to files are captured as a page view so they can be used as a goal conversion in Google Analytics.

4. Allows tracking of clicks on email addresses supplied on your web pages. Email address links are captured as a page view so they can be used as a goal conversion in Google Analytics.

5. Allows the tracking of clicks on external links originating from your website. Again, no updates to your link code required. Links to external websites are tracked as events, so they don't inflate your page view statistics.

---

**Options:**

The plugin has 11 default options, which can be overwritten as required:

```
'trackCrossDomain': false,
// Whether cross-domain tracking is enabled. Default is false
```
```
'domains': '',
// The domains to be tracked when trackCrossDomain is true. Specified as an array or a comma separated string
```
```
'trackAlternatePropertyIDs': false,
// Whether tracking multiple Property IDs is enabled. Default is false
```
```
'alternatePropertyIDs': ['isd2'],
// The Property IDs to be tracked. Specfied as an array or a comma separated string. Defaults to 'isd2'
```
```
'trackFiles': true,
// Whether file tracking is enabled. Default is true
```
```
'trackFilesAsEvent': false,
// Whether file tracking should be tracked as an event (true) instead of a page view. Default is false
```
```
'appendFiles': true,
// Whether custom file types are appended to the default files (true) or replace the them. Default is false
```
```
'defaultFiles': ['.csv', '.doc', '.pdf', '.ppt', '.rar', '.rtf', '.txt', '.xls', '.zip'],
// The default file extensions to track. Note: .doc will also track .docx etc
```
```
'files': '',
// Other file extensions to track. Specified as an array or a comma separated string
```
```
'eventCategory': 'External',
// The category name to assign to (external) links tracked as _trackEvent
```
```
'delay': 200
// WebKit only. A delay before the link href is followed to allow the tracking events to fire correctly
```

---

**Usage:**

1. Add the standard Google Analytics Tracking tag (https://developers.google.com/analytics/devguides/collection/gajs/asyncTracking) before the closing ``</head>`` of your page. You will need to modify the standard tracking tag code if you are tracking cross-domain and/or if you are tracking multiple profiles

2. Add a reference to the jQuery library (preferably before the closing ``</body>``)

3. Add a reference to the jQuery Google Analytics Tracker plugin after jQuery

4. Call the plugin on links you want to track

---

**Examples:**

*Simplest tracking of all links, using default options*

```
$('a').isdAnalyticsTracker();
```

*Cross-domain tracking of all links*

```
$('a').isdAnalyticsTracker({
	'trackCrossDomain':  true,
	'domains': ['yourdomain1.com', 'yourdomain2.com']
});
```

*Cross-domain tracking of all links with multiple Property IDs*

```
$('a').isdAnalyticsTracker({
	'trackCrossDomain':  true,
	'domains': ['yourdomain1.com', 'yourdomain2.com'],
	'trackAlternatePropertyIDs': true,
	'alternatePropertyIDs': ['isd2', 'isd3']
});
```

*Tracking additional image file extensions as events*

```
$('a').isdAnalyticsTracker({
	'trackFilesAsEvent': true,
	'files': ['.ai', '.eps', '.psd']
});
```

---

More detailed info and a test page can be found here: http://www.searchanddisplay.com.au/index.php/solutions-and-services/google-analytics-jquery-plugin