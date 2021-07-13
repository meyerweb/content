---
title: Temporal.ZonedDateTime.prototype.getISOFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/getISOFields
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>getISOFields()</code></strong> method returns an object containing the ISO 8601 calendar fields and values that correspond to the date and time.</span> This method is mainly useful if you are implementing a custom calendar.</p>

## Syntax

```js
getISOFields()
```

### Parameters

None.

### Return value

An object containing the `isoYear`, `isoMonth`, `isoDay`, `isoHour`,
`isoMinute`, `isoSecond`, `isoMillisecond`, `isoMicrosecond`, `isoNanosecond`,
`offset`, `timeZone`, and `calendar` properties.

## Examples

```js
// get a Temporal.ZonedDateTime in `hebrew` calendar system
zdt = Temporal.ZonedDateTime.from('2019-02-23T03:24:30.000003500[Europe/Rome]').withCalendar('hebrew');

// Month in Hebrew calendar is month 6 of leap year 5779
zdt.month; // => 6
zdt.getISOFields().isoMonth; // => 2

// Instead of calling getISOFields, the pattern below is recommended for most use cases
zdt.withCalendar('iso8601').month; // => 2
```
