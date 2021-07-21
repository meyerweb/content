---
title: Temporal.PlainTime.prototype.add()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/add
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

The **`add()`** method creates a new
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}} object
by adding a duration to a
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}
object.Adding a negative duration is equivalent to
{{jsxref('Temporal.PlainTime/subtract','subtracting','','nocode')}}
the absolute value of that duration.

## Syntax

```js
add(duration)
```

### Parameters

- `duration`

  - : An object with properties denoting a duration, such as
    `{ hours: 5, minutes: 30 }`, or a string value such as `PT5H30M`, or a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object.
    If `duration` is not such a string nor a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object,
    then it will be converted to a string as if it were passed to
    {{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}.

    If the addition of the _duration_ to the original time takes it past 24
    hours, the time will be "wrapped around" to zero. Thus, the returned
    wall-clock time may be either in the future or in the past relative to the
    original time, or even the same time.

### Return value

A new {{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}
object representing the wall-clock time indicated by `PlainTime` plus
`duration`.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.add({ minutes: 5, nanoseconds: 800 }); // => 19:44:09.068347005
time.add({ hours: 12 }); // => 07:39:09.068346205
```
