---
title: Temporal.TimeZone.prototype.getInstantFor()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/getInstantFor
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

<p class="summary"><span class="seoSummary">The <strong><code>getInstantFor()</code></strong> method finds the exact time in a time zone at the time of a given calendar date and wall-clock time, even those which may be "skipped" by a change to or from Daylight Saving Time (DST).</span></p>

This method is one way to convert a
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
to a `{{jsxref('Temporal/Instant','Temporal.Instant')}}`. The
result is identical to
`dateTime.toZonedDateTime(timeZone, { disambiguation }).toInstant()`. When
subclassing
`{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}}`, this
method doesn't need to be overridden because the default implementation calls
`{{jsxref('Temporal/TimeZone/getPossibleInstantsFor','timeZone.getPossibleInstantsFor()')}}`,
and if there is more than one possible instant, uses `disambiguation` to pick
which one to return.

## Syntax

```js
getInstantFor(dateTime)
getInstantFor(dateTime, options)
```

### Parameters

- `dateTime`
  - : A calendar date and wall-clock time to convert, represented as a
    `{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
    object or value convertible to one.
- `options` {{optional_inline}}
  - : An object with properties representing options for the operation. The
    following option is recognized:
    - `disambiguation`
      - : How to disambiguate if the date and time given by `dateTime` does not
        exist in the time zone, or exists more than once. Allowed values are:
        - `'compatible'` (default) - Acts like `earlier` for backward
          transitions and `later` for forward transitions.
        - `'earlier'` - The earlier of two possible times.
        - `'later'` - The later of two possible times.
        - `'reject'` - Throw a `RangeError` instead. When interoperating with
          existing code or services, `'compatible'` disambiguation matches the
          behavior of legacy {{jsxref('Date','Date')}} as well as
          libraries like moment.js, Luxon, and date-fns. This mode also matches
          the behavior of cross-platform standards like RFC 5545 (iCalendar).

During "skipped" clock time like the hour after DST starts in the Spring, this
method interprets invalid times using the pre-transition time zone offset if
`compatible` or `later` is used, or the post-transition time zone offset if
`earlier` is used. This behavior avoids exceptions when converting non-existent
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
values to `{{jsxref('Temporal/Instant','Temporal.Instant')}}`,
but it also means that values during these periods will result in a different
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
in "round-trip" conversions to
`{{jsxref('Temporal/Instant','Temporal.Instant')}}` and back
again.

### Return value

A `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object
indicating the exact time in `timeZone` at the time of the calendar date and
wall-clock time at `dateTime`. If `dateTime` is not a
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
object, then it will be converted to one as if it were passed to
`{{jsxref('Temporal/PlainDateTime/from','Temporal.PlainDateTime.from()')}}`.

If the result is earlier or later than the range that
`{{jsxref('Temporal/Instant','Temporal.Instant')}}` can represent
(approximately half a million years centered on the Unix epoch), then a
`RangeError` will be thrown, no matter the value of disambiguation.

## Examples

```js
let dateTime = Temporal.PlainDateTime.from('2021-05-18T11:58:58');
let timeZone = Temporal.TimeZone.from('Asia/Baghdad');
timeZone.getInstantFor(dateTime);
// => Temporal.Instant <2021-05-18T08:58:58Z>
```
