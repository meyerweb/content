---
title: Temporal
slug: Web/JavaScript/Reference/Global_Objects/Temporal
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong>Temporal API</strong> provides an interface for representing dates and times, as well as calculating precise spans of time.</span> Much of it will seem familiar to anyone who has used {{jsxref('Date','Date')}}, but the Temporal API provides a far more powerful and flexible feature set, including built-in understanding of time zones, Daylight Saving status, usage of different calendars, and up to nanosecond precision.</p>

## Built-In Objects

- {{jsxref("Temporal/now", "Temporal.now")}}
  - : Contains several static methods which give information about the current
    time, date, and time zone.

## Classes

- {{jsxref("Temporal/instant", "Temporal.Instant")}}
  - : Represents a single point in time, without regard to calendar or location,
    with a precision in nanoseconds.
- {{jsxref("Temporal/timezone", "Temporal.TimeZone")}}
  - : Represents an IANA time zone, a specific UTC offset, or UTC itself. Time
    zones translate from a date/time in UTC to a local date/time.
- {{jsxref("Temporal/calendar", "Temporal.Calendar")}}
  - : Represents a calendar system, including information on how to do
    arithmetic in that system.
- {{jsxref("Temporal/duration", "Temporal.Duration")}}
  - : Represents a span of time that can be used in date/time arithmetic.
- {{jsxref("Temporal/plaindate", "Temporal.PlainDate")}}
  - : Represents a calendar date independent of any time or time zone.
- {{jsxref("Temporal/plaintime", "Temporal.PlainTime")}}
  - : Represents a wall-clock time, with a precision in nanoseconds, but without
    any date or time zone.
- {{jsxref("Temporal/plaindatetime", "Temporal.PlainDateTime")}}
  - : Represents a calendar date and wall-clock time, with a precision in
    nanoseconds, and without any time zone.
- {{jsxref("Temporal/plainyearmonth", "Temporal.PlainYearMonth")}}
  - : Represents the entirety of a particular month on the calendar, situated
    within a year.
- {{jsxref("Temporal/plainmonthday", "Temporal.PlainMonthDay")}}
  - : Represents a month-and-day object which is not associated with a specific
    year.
- {{jsxref("Temporal/zoneddatetime", "Temporal.ZonedDateTime")}}
  - : Represents a real event that has happened (or will happen) at a particular
    instant from the perspective of a particular region on Earth in a
    time-zone-aware, calendar-aware manner.
