---
title: Temporal.now
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - now
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

The **`Temporal.now`** class provides several methods that give information
about the current time and date.

## Static Methods

- {{jsxref("Temporal/now/instant", "instant()")}}
  - : Returns the current system time in nanoseconds as a new
    {{jsxref('Temporal.Instant','Temporal.Instant')}} object.
- {{jsxref("Temporal/now/timeZone", "timeZone()")}}
  - : Returns the current system time zone as a
    {{jsxref('Temporal.TimeZone','Temporal.TimeZone')}} object.
- {{jsxref("Temporal/now/zonedDateTime", "zonedDateTime()")}}
  - : Returns the current system date, time, time zone, and time zone offset in
    the reckoning of a given calendar as a
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
    object.
- {{jsxref("Temporal/now/zonedDateTimeISO", "zonedDateTimeISO()")}}
  - : Returns the current system date, time, time zone, and time zone offset in
    the reckoning of the ISO 8601 calendar as a
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
    object.
- {{jsxref("Temporal/now/plainDate", "plainDate()")}}
  - : Returns the current system date in the reckoning of a given calendar as a
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    object.
- {{jsxref("Temporal/now/plainDateISO", "plainDateISO()")}}
  - : Returns the current system date in the reckoning of the ISO 8601 calendar
    as a
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    object.
- {{jsxref("Temporal/now/plainTimeISO", "plainTimeISO()")}}
  - : Returns the current system time in the reckoning of the ISO 8601 calendar
    as a
    {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
    object.
- {{jsxref("Temporal/now/plainDateTime", "plainDateTime()")}}
  - : Returns the current system date and time in the reckoning of a given
    calendar as a
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
    object.
- {{jsxref("Temporal/now/plainDateTimeISO", "plainDateTimeISO()")}}
  - : Returns the current system date and time in the reckoning of the ISO 8601
    calendar as a
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
    object.
