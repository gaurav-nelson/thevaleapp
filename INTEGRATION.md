# Integration Guide

This guide explains how to integrate the GitHub issue templates with your app's feedback button.

## URL Format for Pre-filled Issue Forms

To create a link from your app that opens the GitHub issue form with the version pre-filled, use the following URL format:

### Bug Report
```
https://github.com/gaurav-nelson/thevaleapp/issues/new?template=bug_report.yml&version=YOUR_VERSION
```

### Feedback
```
https://github.com/gaurav-nelson/thevaleapp/issues/new?template=feedback.yml&version=YOUR_VERSION
```

### Feature Request
```
https://github.com/gaurav-nelson/thevaleapp/issues/new?template=feature_request.yml&version=YOUR_VERSION
```

### Let User Choose Template
```
https://github.com/gaurav-nelson/thevaleapp/issues/new/choose
```

## Example Implementation

In your app code, you can construct the URL dynamically:

```javascript
// Get the app version from your app's configuration
const appVersion = "1.0.0"; // Replace with your actual version

// Construct the URL
const feedbackUrl = `https://github.com/gaurav-nelson/thevaleapp/issues/new?template=feedback.yml&version=${appVersion}`;

// Open in browser/webview
window.open(feedbackUrl, '_blank');
```

## Query Parameters

The URL format supports pre-filling fields using query parameters:

- `template` - Specifies which template to use (bug_report.yml, feedback.yml, or feature_request.yml)
- `version` - Pre-fills the "App Version" field
- `title` - Pre-fills the issue title (optional)

## Example URLs

### Bug report with version 1.2.3:
```
https://github.com/gaurav-nelson/thevaleapp/issues/new?template=bug_report.yml&version=1.2.3
```

### Feedback with version 1.2.3 and custom title:
```
https://github.com/gaurav-nelson/thevaleapp/issues/new?template=feedback.yml&version=1.2.3&title=App%20is%20great!
```

## Notes

- URL encode special characters in query parameters
- The version field is required in all templates
- Users can still modify the pre-filled values before submitting
