---
title: Temporal.PlainTime.prototype.subtract()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/subtract
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

<p class="summary"><span class="seoSummary">The <strong><code>subtract()</code></strong> method creates a new <code>{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}</code> object by subtracting a duration from a <code>{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}</code> object.</span> Subtracting a negative duration is equivalent to {{jsxref('Temporal.PlainTime/add','adding')}} the absolute value of that duration.</p>

## Syntax

```js
subtract(duration)
```

### Parameters

- `duration`

  - : An object with properties denoting a duration, such as
    `{ hours: 5, minutes: 30 }`, or a string value such as `PT5H30M`, or a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object. If `duration` is not such a string nor a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object, then it will be converted to a string as if it were passed to
    `{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}`.

    If the subtraction of the _duration_ from the original time takes it below 0
    hours, the time will be "wrapped around" to 24 hours. Thus, the returned
    wall-clock time may be either in the future or in the past relative to the
    original time, or even the same time.

### Return value

A new `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
object representing the wall-clock time indicated by `plainTime` minus
`duration`.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.subtract({ minutes: 5, nanoseconds: 800 }); // => 19:34:09.068345405
time.subtract({ hours: 12 }); // => 07:39:09.068346205
```
