---
title: Temporal.TimeZone.prototype.getPossibleInstantsFor()
slug: >-
  Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/getPossibleInstantsFor
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

<p class="summary"><span class="seoSummary">The <strong><code>getPossibleInstantsFor()</code></strong> method finds all the possible exact times that could correspond to a given calendar date and wall-clock time.</span> Normally there is only one possible exact time corresponding to a wall-clock time, but around a daylight saving change, a wall-clock time may not exist, or the same wall-clock time may exist twice in a row.</p>

Although this method is useful for implementing a custom time zone or custom
disambiguation behaviour, usually you won't have to use this method;
`{{jsxref('Temporal/TimeZone/getInstantFor','Temporal.TimeZone.getInstantFor()')}}`
will be more convenient for most use cases. During "skipped" clock time like the
hour after DST starts in the Spring,
`{{jsxref('Temporal/TimeZone/getInstantFor','Temporal.TimeZone.getInstantFor()')}}`
returns a `{{jsxref('Temporal/Instant','Temporal.Instant')}}` (by
default interpreting the
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
using the pre-transition time zone offset), while this method returns zero
results during those skipped periods.

## Syntax

```js
getPossibleInstantsFor(dateTime)
```

### Parameters

- `dateTime`
  - : A calendar date and wall-clock time to convert, represented as a
    `{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
    object, or a value convertible to one.

### Return value

An array of `{{jsxref('Temporal/Instant','Temporal.Instant')}}`
objects, which may be empty. Each object indicates the exact time in `timeZone`
at the time of the calendar date and wall-clock time at `dateTime`. If
`dateTime` is not a
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
object, then it will be converted to one as if it were passed to
`{{jsxref('Temporal/PlainDateTime/from','Temporal.PlainDateTime.from()')}}`.

If the result is earlier or later than the range that
`{{jsxref('Temporal/Instant','Temporal.Instant')}}` can represent
(approximately half a million years centered on the Unix epoch), then a
`RangeError` will be thrown, no matter the value of disambiguation.

## Examples

```js
let dateTime = Temporal.PlainDateTime.from('2021-05-18T11:58:58');
let timeZone = Temporal.TimeZone.from('Asia/Baghdad');
timeZone.getPossibleInstantsFor(dateTime);
// => Array [Temporal.Instant <2021-05-18T08:58:58Z>]
```

```js
let dateTime = Temporal.PlainDateTime.from('2020-11-01T01:34:37');
let timeZone = Temporal.TimeZone.from('America/Chicago');
timeZone.getPossibleInstantsFor(dateTime);
// => Array [Temporal.Instant <2020-11-01T06:34:37Z>, Temporal.Instant <2020-11-01T07:34:37Z>]
```
