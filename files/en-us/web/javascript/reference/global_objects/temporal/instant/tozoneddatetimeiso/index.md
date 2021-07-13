---
title: Temporal.Instant.prototype.toZonedDateTimeISO()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/toZonedDateTimeISO
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toZonedDateTimeISO()</code></strong> method returns a <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object, by supplying a time zone to be combined with the exact instant of the <code>{{jsxref('Temporal.Instant','Temporal.Instant')}}</code> object in the ISO 8601 calendar.</span> If you want to do this using any calendar other than ISO 8601, use {{jsxref('Temporal/Instant/toZonedDateTime','.toZonedDateTime()')}} instead.</p>

## Syntax

```js
toZonedDateTimeISO(timeZone)
```

### Parameters

- `timeZone`
  - : The time zone into which to project the instant. This can be represented
    by a `{{jsxref('Temporal.TimeZone','Temporal.TimeZone')}}`
    object, an object implementing the Temporal time zone protocol, or a value
    that can be converted to a time zone as if it were passed to
    `{{jsxref('Temporal.TimeZone/from','Temporal.TimeZone.from()')}}`.

### Return value

A new
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
object that represents the combination of instant and time zone. If the result
is outside the range that
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
can represent (approximately half a million years centered on the Unix epoch),
then a `RangeError` will be thrown.

## Examples

```js
// Converting a specific exact time to a calendar date / wall-clock time
timestamp = Temporal.Instant.fromEpochSeconds(1553993100);
timestamp.toZonedDateTimeISO('Europe/Berlin'); // => 2019-03-31T01:45:00+01:00[Europe/Berlin]
timestamp.toZonedDateTimeISO('UTC'); // => 2019-03-31T00:45:00+00:00[UTC]
timestamp.toZonedDateTimeISO('-08:00'); // => 2019-03-30T16:45:00-08:00[-08:00]
```
