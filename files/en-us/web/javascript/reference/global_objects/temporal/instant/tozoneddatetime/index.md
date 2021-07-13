---
title: Temporal.Instant.prototype.toZonedDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/toZonedDateTime
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toZonedDateTime()</code></strong> method returns a <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object, by supplying a time zone and calendar to be combined with the exact instant of the <code>{{jsxref('Temporal.Instant','Temporal.Instant')}}</code> object.</span> If you want to do this using the ISO 8601 calendar, use {{jsxref('Temporal/Instant/toZonedDateTimeISO','.toZonedDateTimeISO()')}} instead.</p>

## Syntax

```js
toZonedDateTime(fields)
```

### Parameters

- `fields`

  - : An object with properties to be combined with `instant`. The necessary
    property fields are:

    - `timeZone`

      - : The time zone into which to project the instant. This can be
        represented by a
        `{{jsxref('Temporal.TimeZone','Temporal.TimeZone')}}`
        object, an object implementing the Temporal time zone protocol, or a
        value that can be converted to a time zone as if it were passed to
        `{{jsxref('Temporal.TimeZone/from','Temporal.TimeZone.from()')}}`.

    - `calendar`
      - : The calendar into which to project the instant. This can be
        represented by a
        `{{jsxref('Temporal.Calendar','Temporal.Calendar')}}`
        object, an object implementing the Temporal calendar protocol, or a
        string identifying a calendar that can be passed to
        `{{jsxref('Temporal.Calendar/from','Temporal.Calendar.from()')}}`.

### Return value

A
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
object that represents the combination of instant, time zone, and calendar. If
the result is outside the range that
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
can represent (approximately half a million years centered on the Unix epoch),
then a `RangeError` will be thrown.

## Examples

```js
// What time was the Unix epoch (timestamp 0) in Bell Labs (Murray Hill, New Jersey, USA) in the Gregorian calendar?
epoch = Temporal.Instant.fromEpochSeconds(0);
timeZone = Temporal.TimeZone.from('America/New_York');
epoch.toZonedDateTime({ timeZone, calendar: 'gregory' });
  // => 1969-12-31T19:00:00-05:00[America/New_York][u-ca=gregory]

// What time was the Unix epoch in Tokyo in the Japanese calendar?
timeZone = Temporal.TimeZone.from('Asia/Tokyo');
calendar = Temporal.Calendar.from('japanese');
zdt = epoch.toZonedDateTime({ timeZone, calendar });
  // => 1970-01-01T09:00:00+09:00[Asia/Tokyo][u-ca=japanese]
console.log(zdt.eraYear, zdt.era);
  // => '45 showa'
```
