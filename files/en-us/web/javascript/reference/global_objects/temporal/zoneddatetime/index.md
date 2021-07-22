---
title: Temporal.ZonedDateTime
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime
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

`Temporal.ZonedDateTime` is a time-zone-aware, calendar-aware date-and-time type
that represents a real event that has happened (or will happen) at a particular
instant from the perspective of a particular region on Earth.As the broadest
Temporal type, `Temporal.ZonedDateTime` can be considered a combination of
{{jsxref('Temporal.TimeZone','Temporal.TimeZone')}},
{{jsxref('Temporal.Instant','Temporal.Instant')}}, and
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
(which includes
{{jsxref('Temporal.Calendar','Temporal.Calendar')}}).

As the only Temporal type that persists a time zone, `Temporal.ZonedDateTime` is
optimized for use cases that require a time zone. This means:

- Arithmetic automatically adjusts for DST (Daylight Saving Time), using the
  rules defined in RFC 5545 (iCalendar) and adopted in JavaScript libraries like
  moment.js.
- Creating derived values (e.g. change time to 2:30AM) can avoid worrying that
  the result will be invalid due to the time zone's DST rules.
- Properties are available to easily measure attributes like "length of day" or
  "starting time of day", which may not be the same on all days in all time
  zones due to DST transitions or political changes to the definitions of time
  zones.
- It's easy to flip back and forth between a human-readable representation (like
  {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}})
  and the UTC timeline (like
  {{jsxref('Temporal.Instant','Temporal.Instant')}}) without
  having to do any work to keep the two in sync.
- A date/time, an offset, a time zone, and an optional calendar can be persisted
  in a single string that can be sorted alphabetically by the exact time they
  happened. This behavior is also helpful for developers who are not sure which
  of those components will be needed by later readers of the data.
- Multiple time-zone-sensitive operations can be performed in a chain without
  having to repeatedly provide the same time zone.

A `Temporal.ZonedDateTime` instance can be losslessly converted into every other
Temporal type except
{{jsxref('Temporal.Duration','Temporal.Duration')}}.

## Constructor

- {{jsxref('Temporal/ZonedDateTime/constructor','new Temporal.ZonedDateTime()')}}
  - : Creates a new `Temporal.ZonedDateTime` object which represents a
    time-zone-aware time on a specific date.

## Instance Properties

- {{jsxref('Temporal/ZonedDateTime/year','year')}}
  {{readonlyinline}}
  - : The year in which the date and time occurs.
- {{jsxref('Temporal/ZonedDateTime/month','month')}}
  {{readonlyinline}}
  - : The number of the month in which the date and time occurs.
- {{jsxref('Temporal/ZonedDateTime/monthCode','monthCode')}}
  {{readonlyinline}}
  - : A calendar-specific string identifying the date and time's month in a
    year-independent manner.
- {{jsxref('Temporal/ZonedDateTime/day','day')}}
  {{readonlyinline}}
  - : The day of the month on which the date and time occurs.
- {{jsxref('Temporal/ZonedDateTime/hour','hour')}}
  {{readonlyinline}}
  - : A number that identifies the hour component of the date and time.
- {{jsxref('Temporal/ZonedDateTime/minute','minute')}}
  {{readonlyinline}}
  - : A number that identifies the minute component of the date and time.
- {{jsxref('Temporal/ZonedDateTime/second','second')}}
  {{readonlyinline}}
  - : A number that identifies the second component of the date and time.
- {{jsxref('Temporal/ZonedDateTime/millisecond','millisecond')}}
  {{readonlyinline}}
  - : A number that identifies the millisecond component of the date and time.
- {{jsxref('Temporal/ZonedDateTime/microsecond','microsecond')}}
  {{readonlyinline}}
  - : A number that identifies the microsecond component of the date and time.
- {{jsxref('Temporal/ZonedDateTime/nanosecond','nanosecond')}}
  {{readonlyinline}}
  - : A number that identifies the nanosecond component of the date and time.
- {{jsxref('Temporal/ZonedDateTime/epochSeconds','epochSeconds')}}
  {{readonlyinline}}
  - : The number of full seconds between the `Temporal.zonedDateTime` object and
    the UNIX Epoch.
- {{jsxref('Temporal/ZonedDateTime/epochMilliseconds','epochMilliseconds')}}
  {{readonlyinline}}
  - : The number of full milliseconds between the `Temporal.zonedDateTime`
    object and the UNIX Epoch.
- {{jsxref('Temporal/ZonedDateTime/epochMicroseconds','epochMicroseconds')}}
  {{readonlyinline}}
  - : The number of full microseconds between the `Temporal.zonedDateTime`
    object and the UNIX Epoch.
- {{jsxref('Temporal/ZonedDateTime/epochNanoseconds','epochNanoseconds')}}
  {{readonlyinline}}
  - : The number of full nanoseconds between the `Temporal.zonedDateTime` object
    and the UNIX Epoch.
- {{jsxref('Temporal/ZonedDateTime/calendar','calendar')}}
  {{readonlyinline}}
  - : An object containing the calendar in which the date and time properties
    are interpreted.
- {{jsxref('Temporal/ZonedDateTime/timeZone','timeZone')}}
  {{readonlyinline}}
  - : The persistent time zone of the date and time.
- {{jsxref('Temporal/ZonedDateTime/era','era')}}
  {{readonlyinline}}
  - : The era in which the date and time occurs, in calendar systems that use
    eras.
- {{jsxref('Temporal/ZonedDateTime/eraYear','eraYear')}}
  {{readonlyinline}}
  - : The year of the era in which the date and time occurs, in calendar systems
    that use eras.
- {{jsxref('Temporal/ZonedDateTime/dayOfWeek','dayOfWeek')}}
  {{readonlyinline}}
  - : The weekday number on which the date and time falls.
- {{jsxref('Temporal/ZonedDateTime/dayOfYear','dayOfYear')}}
  {{readonlyinline}}
  - : The ordinal day of the year on which the date and time falls.
- {{jsxref('Temporal/ZonedDateTime/weekOfYear','weekOfYear')}}
  {{readonlyinline}}
  - : The ISO week number in which the date and time falls.
- {{jsxref('Temporal/ZonedDateTime/daysInWeek','daysInWeek')}}
  {{readonlyinline}}
  - : The number of days in the week containing the date and time.
- {{jsxref('Temporal/ZonedDateTime/daysInMonth','daysInMonth')}}
  {{readonlyinline}}
  - : The number of days in the month containing the date and time.
- {{jsxref('Temporal/ZonedDateTime/daysInYear','daysInYear')}}
  {{readonlyinline}}
  - : The number of days in the year containing the date and time.
- {{jsxref('Temporal/ZonedDateTime/monthsInYear','monthsInYear')}}
  {{readonlyinline}}
  - : The number of months in the year containing the date and time.
- {{jsxref('Temporal/ZonedDateTime/inLeapYear','inLeapYear')}}
  {{readonlyinline}}
  - : Indicates whether the date and time occurs in a leap year.
- {{jsxref('Temporal/ZonedDateTime/hoursInDay','hoursInDay')}}
  {{readonlyinline}}
  - : The number of real-world hours between the start of the
    `Temporal.zonedDateTime` object's day to the start of the next calendar day
    in the same time zone.
- {{jsxref('Temporal/ZonedDateTime/startOfDay','startOfDay')}}
  {{readonlyinline}}
  - : The earliest valid local clock time during the given calendar day and time
    zone.
- {{jsxref('Temporal/ZonedDateTime/offsetNanoseconds','offsetNanoseconds')}}
  {{readonlyinline}}
  - : The offset (in nanoseconds) relative to UTC of the
    `Temporal.ZonedDateTime` object's time zone
- {{jsxref('Temporal/ZonedDateTime/offset','offset')}}
  {{readonlyinline}}
  - : The offset (formatted as a string) relative to UTC of the
    `Temporal.ZonedDateTime` object's time zone.

## Static Methods

- {{jsxref('Temporal/ZonedDateTime/from','from()')}}
  - : Creates a new `Temporal.ZonedDateTime` object from another value.
- {{jsxref('Temporal/ZonedDateTime/compare','compare()')}}
  - : Compares two dates and times, and returns an integer indicating which
    comes before the other.

## Instance Methods

- {{jsxref('Temporal/ZonedDateTime/with','with()')}}
  - : Returns a new
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
    object which is a modification of the original `Temporal.ZonedDateTime`
    object using new property values.
- {{jsxref('Temporal/ZonedDateTime/withPlainTime','withPlainTime()')}}
  - : Returns a new
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
    object which is a modification of the original zoned date and time with a
    new time.
- {{jsxref('Temporal/ZonedDateTime/withPlainDate','withPlainDate()')}}
  - : Returns a new
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
    object which is a modification of the original zoned date and time with a
    new date.
- {{jsxref('Temporal/ZonedDateTime/withTimeZone','withTimeZone()')}}
  - : Returns a
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
    object of a zoned date and time projected into a specified time zone.
- {{jsxref('Temporal/ZonedDateTime/withCalendar','withCalendar()')}}
  - : Returns a
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
    object of a zoned date and time projected into a specified calendar.
- {{jsxref('Temporal/ZonedDateTime/add','add()')}}
  - : Creates a new `Temporal.ZonedDateTime` object by adding a duration to a
    `Temporal.ZonedDateTime}` object.
- {{jsxref('Temporal/ZonedDateTime/subtract','subtract()')}}
  - : Creates a new `Temporal.ZonedDateTime` object by subtracting a duration
    from a `Temporal.ZonedDateTime}` object.
- {{jsxref('Temporal/ZonedDateTime/until','until()')}}
  - : Computes the elapsed time between the `Temporal.ZonedDateTime` object and
    another zoned date and time in the future, optionally rounds it, and returns
    it as a {{jsxref('Temporal.Duration','Temporal.Duration')}}
    object.
- {{jsxref('Temporal/ZonedDateTime/since','since()')}}
  - : Computes the elapsed time between the `Temporal.ZonedDateTime` object and
    another zoned date and time in the past, optionally rounds it, and returns
    it as a {{jsxref('Temporal.Duration','Temporal.Duration')}}
    object.
- {{jsxref('Temporal/ZonedDateTime/round','round()')}}
  - : Creates a new `Temporal.ZonedDateTime` object by rounding the date and
    time.
- {{jsxref('Temporal/ZonedDateTime/equals','equals()')}}
  - : Determines whether a `Temporal.ZonedDateTime` object is exactly the same
    as another zoned date and time.
- {{jsxref('Temporal/ZonedDateTime/toInstant','toInstant()')}}
  - : Returns a new
    {{jsxref('Temporal.Instant','Temporal.Instant')}} object that
    corresponds to the exact instant of the zoned date and time.
- {{jsxref('Temporal/ZonedDateTime/toPlainDate','toPlainDate()')}}
  - : Returns a new
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    object that corresponds to the date (not time) components of the zoned date
    and time.
- {{jsxref('Temporal/ZonedDateTime/toPlainTime','toPlainTime()')}}
  - : Returns a new
    {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
    object that corresponds to the time (not date) components of the zoned date
    and time.
- {{jsxref('Temporal/ZonedDateTime/toPlainDateTime','toPlainDateTime()')}}
  - : Returns a new
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
    object that corresponds to the date and time (but not time zone) components
    of the zoned date and time.
- {{jsxref('Temporal/ZonedDateTime/toPlainYearMonth','toPlainYearMonth()')}}
  - : Returns a
    {{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
    object that corresponds to the year and month components of the zoned date
    and time.
- {{jsxref('Temporal/ZonedDateTime/toPlainMonthDay','toPlainMonthDay()')}}
  - : Returns a
    {{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
    object that corresponds to the month and day components of the zoned date
    and time.
- {{jsxref('Temporal/ZonedDateTime/toLocaleString','toLocaleString()')}}
  - : Returns a human-readable, language-sensitive representation of the zoned
    date and time.
- {{jsxref('Temporal/ZonedDateTime/toString','toString()')}}
  - : Returns a string representing the zoned date and time in ISO 8601 format.
- {{jsxref('Temporal/ZonedDateTime/toJSON','toJSON()')}}
  - : Returns a string representing the zoned date and time in ISO 8601 format.
- {{jsxref('Temporal/ZonedDateTime/getISOFields','getISOFields()')}}
  - : Returns an object containing the ISO 8601 calendar fields and values
    corresponding to the zoned date and time.
- {{jsxref('Temporal/ZonedDateTime/valueOf','valueOf()')}}
  - : Overrides
    {{jsxref('Object/valueOf','Object.prototype.valueOf')}} and
    **always** throws an exception.
