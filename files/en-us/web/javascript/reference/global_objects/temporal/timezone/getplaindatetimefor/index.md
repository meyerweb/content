---
title: Temporal.TimeZone.prototype.getPlainDateTimeFor()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/getPlainDateTimeFor
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

The **`getPlainDateTimeFor()`** method returns a
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object indicating the calendar date and wall-clock time in `timeZone`, according
to the reckoning of `calendar`, at the exact time indicated by `instant`.

This method is one way to convert a
{{jsxref('Temporal/Instant','Temporal.Instant')}} to a
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}.
When subclassing
{{jsxref('Temporal/TimeZone','Temporal.TimeZone</code>')}},
this method doesn't need to be overridden because the default implementation
creates a
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}} from instant using the result of calling {{jsxref('Temporal/TimeZone/getOffsetNanosecondsFor','timeZone.getOffsetNanosecondsFor()')}}.`

`SyntaxgetPlainDateTimeFor(instant) getPlainDateTimeFor(instant, calendar)
ParametersinstantThe point in time to yield a time zone offset from UTC in
nanoseconds. If instant is not a
{{jsxref('Temporal/Instant','Temporal.Instant')}} object, then it
will be converted to one as if it were passed to
{{jsxref('Temporal/Instant/from','Temporal.Instant.from()')}}.calendar
{{optional_inline}}A
{{jsxref('Temporal/Calendar','Temporal.Calendar')}} object, or
a plain object, or a calendar identifier. If no calendar is supplied, the ISO
8601 calendar will be used.Return value

A
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object.

Examples// Getting the UTC offset for a time zone at a particular time timestamp
= Temporal.Instant.fromEpochSeconds(1553993100); tz =
Temporal.TimeZone.from('Europe/Berlin'); tz.getPlainDateTimeFor(timestamp); //
=> 2019-03-31T01:45:00 // TimeZone with a fixed UTC offset tz =
Temporal.TimeZone.from('-08:00'); tz.getPlainDateTimeFor(timestamp); // =>
2019-03-30T16:45:00 // UTC is always 0 offset tz =
Temporal.TimeZone.from('UTC'); tz.getPlainDateTimeFor(timestamp); // =>
2019-03-31T00:45:00

// Differences between DST and non-DST tz =
Temporal.TimeZone.from('Europe/London');
tz.getPlainDateTimeFor('2020-08-06T15:00Z'); // => 2020-08-06T16:00:00
tz.getPlainDateTimeFor('2020-11-06T01:00Z'); // => 2020-11-06T01:00:00`
