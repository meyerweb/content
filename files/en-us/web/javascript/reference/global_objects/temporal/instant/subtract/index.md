---
title: Temporal.Instant.prototype.subtract()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/subtract
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

The **`subtract()`** method creates a new
{{jsxref('Temporal/Instant','Temporal.Instant')}} object by
subtracting a span of time from the
{{jsxref('Temporal/Instant','Temporal.Instant')}}.Subtracting a
negative duration from the instant is equivalent to
{{jsxref('Temporal.Instant/add','adding','','nocode')}} the
absolute value of that duration.

## Syntax

```js
subtract(duration);
```

### Parameters

- `duration`

  - : An object with properties denoting a duration, such as
    `{ hours: 5, minutes: 30 }`, or a string such as `PT5H30M`, or a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object.
    If `duration` is not such a string nor a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object,
    then it will be converted to one as if it were passed to
    {{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}.

    Note that the` years`, `months`, `weeks`, and `days` fields of `duration`
    must be zero.
    {{jsxref('Temporal/Instant','Temporal.Instant')}} is
    independent of time zones and calendars, and so years, months, weeks, and
    days may be different lengths depending on which calendar or time zone they
    are reckoned in. This makes an subtractition with those units ambiguous. If
    you need to do this, convert the
    {{jsxref('Temporal/Instant','Temporal.Instant')}} to a
    {{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
    by specifying the desired calendar and time zone, subtract the duration with
    {{jsxref('Temporal/PlainDateTime/subtract','Temporal.PlainDateTime.subtract()')}},
    and then convert it back to
    {{jsxref('Temporal/Instant','Temporal.Instant')}}.

### Return value

A new {{jsxref('Temporal/Instant','Temporal.Instant')}} object
representing the exact time indicated by `instant` minus `duration`. If the
result is earlier or later than the range that
{{jsxref('Temporal/Instant','Temporal.Instant')}} can represent
(just over half a million years centered on the Unix epoch), a `RangeError` will
be thrown.

## Examples

```js
// Temporal.Instant representing one hour ago from right now
Temporal.now.instant().subtract({ hours: 1 });
oneHour = Temporal.Duration.from({ hours: 1 });
Temporal.now.instant().subtract(oneHour);
```
