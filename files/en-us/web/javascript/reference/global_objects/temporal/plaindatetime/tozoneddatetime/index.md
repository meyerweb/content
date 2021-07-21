---
title: Temporal.PlainDateTime.prototype.toZonedDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/toZonedDateTime
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toZonedDateTime()`** method returns a
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object, by supplying a time zone to be combined with the date and time of the
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object.

## Syntax

```js
toZonedDateTime(timeZone)
toZonedDateTime(timeZone, options)
```

### Parameters

- `timeZone`

  - : The time zone to be combined with the date and time. This can be
    represented by a
    {{jsxref('Temporal.TimeZone','Temporal.TimeZone')}} object,
    an object implementing the Temporal time zone protocol, or a value that can
    be converted to a time zone as if it were passed to
    {{jsxref('Temporal.TimeZone/from','Temporal.TimeZone.from()')}}.

- `options` {{ optional_inline }}

  - : An object containing properties that represent options for constructing
    the new Temporal object. These are:

    - `disambiguation`

      - : How to disambiguate if the date and time do not exist in the time
        zone, or exist more than once. Allowed values are:

        - `'compatible'` (default)
          - : Acts like `'earlier'` for backward transitions and `'later'` for
            forward transitions.
        - `'earlier'`
          - : The earlier of the two possible times.
        - `'later'`
          - : The later of the two possible times.
        - `'reject'` \* : Throw a `RangeError` instead. When interoperating with
          existing code or services, `'compatible'` matches the behavior of
          legacy {{jsxref('Date')}} as well as libraries like moment.js,
          Luxon, and date-fns. This mode also matches the behavior of
          cross-platform standards like RFC 5545 (iCalendar).

        During "skipped" clock time like the hour after DST starts in the
        Spring, this method interprets invalid times using the pre-transition
        time zone offset if `'compatible'` or `'later'` is used, or if the
        post-transition time zone offset if `'earlier'` is used. This behavior
        avoids exceptions when converting non-existent
        {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
        values to
        {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}},
        but it also means that values during these periods will result in a
        different
        {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
        than doing "round-trip" conversions to
        {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
        and back again.

### Return value

A
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object that represents the combination of date, time, and time zone. If the
result is outside the range that
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
can represent (approximately half a million years centered on the Unix epoch),
then a `RangeError` will be thrown.

## Examples

```js
var now = Temporal.PlainDateTime.from('2021-05-18T11:58:58');
// =>
now.toZonedDateTime('America/New_York');
// => 2021-05-18T11:58:58-04:00[America/New_York]
now.toZonedDateTime('Japan');
// => 2021-05-18T11:58:58+09:00[Asia/Tokyo]
```
