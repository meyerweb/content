---
title: Temporal.PlainDateTime.prototype.withPlainTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/withPlainTime
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`withPlainTime()`** method returns a new
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object which is a modification of the original date and time with a new
time.This method is similar to
{{jsxref('Temporal.PlainDateTime/with','.with()')}}, but with a
few important differences:

- `withPlainTime()` accepts strings, Temporal objects, or objects.
  {{jsxref('Temporal.PlainDateTime/with','.with()')}} only
  accepts objects, and does not accept strings nor
  {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
  objects, because they can contain calendar information.
- `withPlainTime()` defaults all missing time units to zero, whereas
  {{jsxref('Temporal.PlainDateTime/with','.with()')}} only
  changes units that are present in the input object.

## Syntax

```js
withPlainTime(plainTime)
```

### Parameters

- `plainTime`
  - : The clock time that should replace the current clock time of the original
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
    object. An object containing some or all of the properties accepted by
    {{jsxref('Temporal/PlainDateTime/from','Temporal.PlainDateTime.from()')}}.
    Valid input to `withPlainTime()` is the same as valid input to
    {{jsxref('Temporal/PlainTime/from','Temporal.PlainTime.from()')}}:
    strings like `12:15:36`, plain objects like `{ hour: 20, minute: 30 }`, or
    Temporal objects that contain time fields:
    {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}},
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}},
    or
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}.

### Return value

A new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object.

## Examples

```js
dt = Temporal.ZonedDateTime.from('2015-12-07T03:24:30.000003500');
dt.withPlainTime({ hour: 10 }); // => 2015-12-07T10:00:00
time = Temporal.PlainTime.from('11:22');
dt.withPlainTime(time); // => 2015-12-07T11:22:00
dt.withPlainTime('12:34'); // => 2015-12-07T12:34:00

// easier for chaining
dt.add({ days: 2, hours: 22 }).withPlainTime('00:00'); // => 2015-12-10T00:00:00
```
