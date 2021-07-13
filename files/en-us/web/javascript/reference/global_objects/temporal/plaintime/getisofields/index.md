---
title: Temporal.PlainTime.prototype.getISOFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/getISOFields
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>getISOFields()</code></strong> method returns an object containing the ISO 8601 calendar fields and values that correspond to the wall-clock time.</span> This method exists for forward compatibility with custom calendars.</p>

## Syntax

```js
getISOFields()
```

### Parameters

None.

### Return value

An object containing the `isoHour`, `isoMinute`, `isoSecond`, `isoMillisecond`,
`isoMicrosecond`, `isoNanosecond`, and `calendar` properties.

## Examples

```js
time = Temporal.PlainTime.from('03:20:00');
f = time.getISOFields();
f.isoHour; // => 3
f.isoMinute; // => 20
f.isoSecond; // => 0
```
