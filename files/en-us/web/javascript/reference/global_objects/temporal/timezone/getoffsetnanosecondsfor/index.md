---
title: Temporal.TimeZone.prototype.getOffsetNanosecondsFor()
slug: >-
  Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/getOffsetNanosecondsFor
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>getOffsetNanosecondsFor()</code></strong> method returns the <abbr title="Coordinated Universal Time">UTC</abbr> offset of a given time, in nanoseconds.</span> This method is similar to <code>{{jsxref('Temporal/TimeZone/getOffsetStringFor','timeZone.getOffsetStringFor()')}}</code>, but it returns the offset as a number of nanoseconds instead of a formatted string.</p>

Note that only
`{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}}` objects
constructed from an IANA time zone name may have DST transitions; those
constructed from a UTC offset do not. If `timeZone` is a UTC offset time zone,
the return value of this method is always the same regardless of `instant`.

## Syntax

```js
getOffsetNanosecondsFor(instant)
```

### Parameters

- `instant`
  - : The point in time to yield a time zone offset from UTC. If `instant` is
    not a `{{jsxref('Temporal/Instant','Temporal.Instant')}}`
    object, then it will be converted to one as if it were passed to
    `{{jsxref('Temporal/Instant/from','Temporal.Instant.from()')}}`.

### Return value

A number indicating the UTC offset of the given time in nanoseconds.

## Examples

```js
// Getting the UTC offset for a time zone at a particular time
timestamp = Temporal.Instant.fromEpochSeconds(1553993100);
tz = Temporal.TimeZone.from('Europe/Berlin');
tz.getOffsetNanosecondsFor(timestamp); // => 3600000000000

// TimeZone with a fixed UTC offset
tz = Temporal.TimeZone.from('-08:00');
tz.getOffsetNanosecondsFor(timestamp); // => -28800000000000
// UTC is always 0 offset
tz = Temporal.TimeZone.from('UTC');
tz.getOffsetNanosecondsFor(timestamp); // => 0

// Differences between DST and non-DST
tz = Temporal.TimeZone.from('Europe/London');
tz.getOffsetNanosecondsFor('2020-08-06T15:00Z'); // => 3600000000000
tz.getOffsetNanosecondsFor('2020-11-06T01:00Z'); // => 0
```
