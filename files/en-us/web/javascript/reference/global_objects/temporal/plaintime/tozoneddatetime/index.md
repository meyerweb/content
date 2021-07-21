---
title: Temporal.PlainTime.prototype.toZonedDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/toZonedDateTime
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toZonedDateTime()`** method converts a
{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}} object
into a
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object, by supplying a date and time zone to be combined with the wall-clock
time of the original
{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}} object.

## Syntax

```js
toZonedDateTime(zonedDate)
```

### Parameters

- `zonedDate`
  - : An object representing the date and time zone to be combined with the
    wall-clock time via two properties:
    - `plaindate`
      - : A date represented by a
        {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
        object, or a value that can be converted to one as if it were passed to
        {{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}.
    - `timeZone`
      - : A time zone represented by a
        {{jsxref('Temporal.TimeZone','Temporal.TimeZone')}}
        object, an object implementing the time zone protocol, or a value that
        can be converted to one as if it were passed to
        {{jsxref('Temporal.TimeZone/from','Temporal.TimeZone.from()')}}.

### Return value

A
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object that represents the combination of date, time zone, and wall-clock time.
If the result is outside the range that
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
can represent (approximately half a million years centered on the Unix epoch),
then a `RangeError` will be thrown.

## Examples

```js
plainTime = Temporal.PlainTime.from('15:23:30.003');
plainDate = Temporal.PlainDate.from('2006-08-24');
plainTime.toZonedDateTime({ timeZone: 'America/Los_Angeles', plainDate });
  // => 2006-08-24T15:23:30.003-07:00[America/Los_Angeles]
```
