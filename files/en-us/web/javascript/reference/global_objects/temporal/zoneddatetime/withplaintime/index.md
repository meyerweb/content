---
title: Temporal.ZonedDateTime.prototype.withPlainTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/withPlainTime
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`withPlainTime()`** method returns a new
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object which is a modification of the original date and time with a new
time.This method is similar to
{{jsxref('Temporal.ZonedDateTime/with','.with()')}}, but with a
few important differences:

- `withPlainTime()` accepts strings, Temporal objects, or objects.
  {{jsxref('Temporal.ZonedDateTime/with','.with()')}} only
  accepts objects, and does not accept strings nor
  {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
  objects, because they can contain calendar information.
- `withPlainTime()` defaults all missing time units to zero, whereas
  {{jsxref('Temporal.ZonedDateTime/with','.with()')}} only
  changes units that are present in the input object.

## Syntax

```js
withPlainTime(plainTime)
```

### Parameters

- `plainTime`
  - : The clock time that should replace the current clock time of the original
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
    object. Valid input to `withPlainTime()` is the same as valid input to
    {{jsxref('Temporal/PlainTime/from','Temporal.PlainTime.from()')}}:
    strings like `12:15:36`, plain objects like `{ hour: 20, minute: 30 }`, or
    Temporal objects that contain time fields:
    {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}},
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}},
    or
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}.

### Return value

A new
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('2015-12-07T03:24:30.000003500-08:00[America/Los_Angeles]');
zdt.withPlainTime({ hour: 10 }); // => 2015-12-07T10:00:00-08:00[America/Los_Angeles]
time = Temporal.PlainTime.from('11:22');
zdt.withPlainTime(time); // => 2015-12-07T11:22:00-08:00[America/Los_Angeles]
zdt.withPlainTime('12:34'); // => 2015-12-07T12:34:00-08:00[America/Los_Angeles]

// easier for chaining
zdt.add({ days: 2, hours: 22 }).withPlainTime('00:00'); // => 2015-12-10T00:00:00-08:00[America/Los_Angeles]
```
