---
title: Temporal.PlainDate.prototype.toZonedDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/toZonedDateTime
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toZonedDateTime()`** method converts a
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object
into a
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object, by supplying a wall-clock time and time zone to be combined with the
date of the
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object.

## Syntax

```js
toZonedDateTime(zonedTime)
```

### Parameters

- `zonedTime`

  - : An object representing the date and time zone to be combined with the
    wall-clock time via two properties:

    - `timeZone`
      - : A time zone represented by a
        {{jsxref('Temporal.TimeZone','Temporal.TimeZone')}}
        object, an object implementing the Temporal time zone protocol, or a
        value that can be converted to one as if it were passed to
        {{jsxref('Temporal.TimeZone/from','Temporal.TimeZone.from()')}}.
    - `plainTime` {{ optional_inline }}

      - : A time represented by a
        {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
        object, or a value that can be converted to one as if it were passed to
        {{jsxref('Temporal.PlainTime/from','Temporal.PlainTime.from()')}}.

        If no `plainTime` is provided, it defaults to the first valid local time
        in `timeZone` on the calendar date. Usually this is midnight (`00:00`),
        but may be a different time in rare circumstances like DST starting at
        midnight.

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
plainDate = Temporal.PlainDate.from('2006-08-24');
plainTime = Temporal.PlainTime.from('15:23:30.003');
plainDate.toZonedDateTime({ timeZone: 'America/Los_Angeles', plainTime });
// => 2006-08-24T15:23:30.003-07:00[America/Los_Angeles]
plainDate.toZonedDateTime({ timeZone: 'America/Los_Angeles' });
// => 2006-08-24T00:00:00-07:00[America/Los_Angeles]
```
