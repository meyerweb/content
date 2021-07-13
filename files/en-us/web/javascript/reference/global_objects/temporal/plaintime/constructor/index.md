---
title: Temporal.PlainTime constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/constructor
tags:
  - Class
  - JavaScript
  - Time
  - constructor
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The constructor for a <code>{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}</code> object.</span> Use this constructor if you have the correct parameters for the time as individual number values. Otherwise, use <code>{{jsxref('Temporal.PlainTime/from','Temporal.PlainTime.from()')}}</code>, which accepts more kinds of input and allows control of value overflow behaviour.</p>

## Syntax

```js
new Temporal.PlainTime()
new Temporal.PlainTime(isoHour)
new Temporal.PlainTime(isoHour, isoMinute)
new Temporal.PlainTime(isoHour, isoMinute, isoSecond)
new Temporal.PlainTime(isoHour, isoMinute, isoSecond, isoMillisecond)
new Temporal.PlainTime(isoHour, isoMinute, isoSecond, isoMillisecond, isoMillisecond)
new Temporal.PlainTime(isoHour, isoMinute, isoSecond, isoMillisecond, isoMillisecond, isoNanosecond)
```

### Parameters

All parameters are numbers, and default to `0` (zero).

- `isoHour` {{optional_inline}}
  - : An hour of the day, ranging from 0 to 23, inclusive.
- `isoMinute` {{optional_inline}}
  - : A number of minutes, ranging from 0 to 59, inclusive.
- `isoSecond` {{optional_inline}}
  - : A number of seconds, ranging from 0 to 59, inclusive.
- `isoMillisecond` {{optional_inline}}
  - : A number of milliseconds, ranging from 0 to 999, inclusive.
- `isoMicrosecond` {{optional_inline}}
  - : A number of microseconds, ranging from 0 to 999, inclusive.
- `isoNanosecond` {{optional_inline}}
  - : A number of nanoseconds, ranging from 0 to 999, inclusive.

### Return value

A new `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
object.

## Examples

```js
// Leet hour
leetTime = new Temporal.PlainTime(13, 37); // => 13:37:00
```
