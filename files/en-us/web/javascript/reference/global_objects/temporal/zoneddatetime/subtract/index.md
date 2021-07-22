---
title: Temporal.ZonedDateTime.prototype.subtract()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/subtract
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
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object by subtracting a duration from a
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object.Subtracting a negative duration is equivalent to
{{jsxref('Temporal.ZonedDateTime/add','adding','','nocode')}}
the absolute value of that duration.

Subtraction is performed according to rules defined in RFC 5545 (iCalendar):

- Subtract the date portion of a duration using calendar days, as in
  {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}.
  The result will automatically adjust for DST (Daylight Saving Time) using the
  rules of this instance's
  {{jsxref('Temporal.ZonedDateTime/timeZone','timeZone')}}
  property.
- Subtract the time portion of a duration using real-world time, as in
  {{jsxref('Temporal.Instant','Temporal.Instant')}}.
- Subtraction (even when using a negative duration) is performed in order from
  largest unit to smallest unit.
- If a result is ambiguous or invalid due to a time zone offset transition, the
  later of the two possible instants will be used for time-skipped transitions
  and the earlier of the two possible instants will be used for time-repeated
  transitions. This behavior corresponds to the default
  `disambiguation: 'compatible'` option used in
  {{jsxref('Temporal.ZonedDateTime/from','.from()')}}, and used
  by legacy {{jsxref('Date','Date','','nocode')}} and moment.js.

These rules make arithmetic with
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
"DST-safe", which means that the results most closely match the expectations of
both real-world users and implementers of other standards-compliant calendar
applications. These expectations include:

- Subtracting days should keep clock time consistent across DST transitions.
- Subtracting the time portion of a duration should ignore DST transitions.
- There should be a consistent and relatively-unsurprising order of operations.
- If results are at or near a DST transition, ambiguities should be handled
  automatically (no crashing) and deterministically.

## Syntax

```js
subtract(duration)
subtract(duration, options)
```

### Parameters

- `duration`

  - : An object with properties denoting a duration, such as `{ days: 5 }`, or a
    string value such as `P5D`, or a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object.
    If `duration` is not such a string nor a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object,
    then it will be converted to a string as if it were passed to
    {{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}.

    Some subtractions may be ambiguous, because months have different lengths.
    For example, subtracting `{ months: 1 }` from October 31 would result in
    September 31, which doesn't exist. In such cases, the `overflow` option (see
    below) governs the result.

- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainDate` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _duration_ are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'` \* : Out-of-range values will cause the function to throw a
          `RangeError`.
          > **Note:** The `overflow` option has no effect in the default ISO
          > calendar, because a year is always 12 months and therefore not
          > ambiguous. However, `overflow` may have an effect in calendars where
          > years can be different numbers of months.

### Return value

A new
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object representing the calendar date indicated by `oldDateTime` minus
`duration`.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('2020-03-09T00:00-07:00[America/Los_Angeles]');
// Add a day to get midnight on the day after DST starts
earlierDay = zdt.subtract({ days: 1 });
  // => 2020-03-08T00:00:00-08:00[America/Los_Angeles]
  // Note that the new offset is different, indicating the result is adjusted for DST.
earlierDay.since(zdt, { largestUnit: 'hours' }).hours;
  // => -23
  // because one clock hour lost to DST

earlierHours = zdt.subtract({ hours: 24 });
  // => 2020-03-07T23:00:00-08:00[America/Los_Angeles]
  // Subtracting time units doesn't adjust for DST. Result is 11:00PM: 24 real-world
  // hours earlier because a clock hour was skipped by DST.
earlierHours.since(zdt, { largestUnit: 'hours' }).hours; // => -24
```
