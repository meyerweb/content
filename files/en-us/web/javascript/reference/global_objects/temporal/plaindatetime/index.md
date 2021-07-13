---
title: Temporal.PlainDateTime
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime
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

<p class="summary"><span class="seoSummary">A <code>Temporal.PlainDateTime</code> represents a calendar date and wall-clock time, with a precision in nanoseconds, and without any time zone.</span> Because <code>Temporal.PlainDateTime</code> does not represent an exact point in time, most date/time use cases are better handled using exact time types like <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> and <code>{{jsxref('Temporal.Instant','Temporal.Instant')}}</code>.</p>

That said, there are cases where Temporal.PlainDateTime is the correct type to
use. For example:

- Modeling events that happen at the same local time in every time zone. For
  example, the British Commonwealth observes a two minute silence every November
  11th at 11:00AM in local time.
- Representing time-zone-specific events where the time zone is not stored
  together with the date/time data.
- Passing data to/from a component that is unaware of time zones, such as a
  date/time picker.
- Cases where time zone is irrelevant; e.g., a sleep-tracking device that only
  cares about the local time you went to sleep and woke up.
- Parsing local time from ISO 8601 strings like 2020-04-09T16:08-08:00 that have
  a numeric offset without an IANA time zone.
- Performing date-and-time arithmetic that deliberately ignores DST.

## Constructor

- `{{jsxref('Temporal/PlainDateTime/constructor','new Temporal.PlainDateTime()')}}`
  - : Creates a new `Temporal.PlainDateTime` object which represents a
    wall-clock time on a specific date.

## Instance Properties

- `{{jsxref('Temporal/PlainDateTime/year','year')}}`
  {{readonlyinline}}
  - : The year in which the date and time occurs.
- `{{jsxref('Temporal/PlainDateTime/era','era')}}`
  {{readonlyinline}}
  - : The era in which the date and time occurs, in calendar systems that use
    eras.
- `{{jsxref('Temporal/PlainDateTime/eraYear','eraYear')}}`
  {{readonlyinline}}
  - : The year of the era in which the date and time occurs, in calendar systems
    that use eras.
- `{{jsxref('Temporal/PlainDateTime/month','month')}}`
  {{readonlyinline}}
  - : The number of the month in which the date and time occurs.
- `{{jsxref('Temporal/PlainDateTime/monthCode','monthCode')}}`
  {{readonlyinline}}
  - : A calendar-specific string identifying the date and time's month in a
    year-independent manner.
- `{{jsxref('Temporal/PlainDateTime/day','day')}}`
  {{readonlyinline}}
  - : The day of the month on which the date and time occurs.
- `{{jsxref('Temporal/PlainDateTime/hour','hour')}}`
  {{readonlyinline}}
  - : A number that identifies the hour component of the date and time.
- `{{jsxref('Temporal/PlainDateTime/minute','minute')}}`
  {{readonlyinline}}
  - : A number that identifies the minute component of the date and time.
- `{{jsxref('Temporal/PlainDateTime/second','second')}}`
  {{readonlyinline}}
  - : A number that identifies the second component of the date and time.
- `{{jsxref('Temporal/PlainDateTime/millisecond','millisecond')}}`
  {{readonlyinline}}
  - : A number that identifies the millisecond component of the date and time.
- `{{jsxref('Temporal/PlainDateTime/microsecond','microsecond')}}`
  {{readonlyinline}}
  - : A number that identifies the microsecond component of the date and time.
- `{{jsxref('Temporal/PlainDateTime/nanosecond','nanosecond')}}`
  {{readonlyinline}}
  - : A number that identifies the nanosecond component of the date and time.
- `{{jsxref('Temporal/PlainDateTime/calendar','calendar')}}`
  {{readonlyinline}}
  - : An object containing the calendar in which the date and time properties
    are interpreted.
- `{{jsxref('Temporal/PlainDateTime/dayOfWeek','dayOfWeek')}}`
  {{readonlyinline}}
  - : The weekday number on which the date and time falls.
- `{{jsxref('Temporal/PlainDateTime/dayOfYear','dayOfYear')}}`
  {{readonlyinline}}
  - : The ordinal day of the year on which the date and time falls.
- `{{jsxref('Temporal/PlainDateTime/weekOfYear','weekOfYear')}}`
  {{readonlyinline}}
  - : The ISO week number in which the date and time falls.
- `{{jsxref('Temporal/PlainDateTime/daysInWeek','daysInWeek')}}`
  {{readonlyinline}}
  - : The number of days in the week containing the date and time.
- `{{jsxref('Temporal/PlainDateTime/daysInMonth','daysInMonth')}}`
  {{readonlyinline}}
  - : The number of days in the month containing the date and time.
- `{{jsxref('Temporal/PlainDateTime/daysInYear','daysInYear')}}`
  {{readonlyinline}}
  - : The number of days in the year containing the date and time.
- `{{jsxref('Temporal/PlainDateTime/monthsInYear','monthsInYear')}}`
  {{readonlyinline}}
  - : The number of months in the year containing the date and time.
- `{{jsxref('Temporal/PlainDateTime/inLeapYear','inLeapYear')}}`
  {{readonlyinline}}
  - : Indicates whether the date and time occurs in a leap year.

## Static Methods

- `{{jsxref('Temporal/PlainDateTime/from','from()')}}`
  - : Creates a new `Temporal.PlainDateTime` object from another value.
- `{{jsxref('Temporal/PlainDateTime/compare','compare()')}}`
  - : Compares two dates and returns an integer indicating which comes before
    the other.

## Instance Methods

- `{{jsxref('Temporal/PlainDateTime/with','with()')}}`
  - : Returns a new `Temporal.PlainDateTime` object which is a modification of
    the original object using new property values.
- `{{jsxref('Temporal/PlainDateTime/withPlainTime','withPlainTime()')}}`
  - : Returns a new `Temporal.PlainDateTime` object which is a modification of
    the original date and time with a new time.
- `{{jsxref('Temporal/PlainDateTime/withPlainDate','withPlainDate()')}}`
  - : Returns a new `Temporal.PlainDateTime` object which is a modification of
    the original date and time with a new date.
- `{{jsxref('Temporal/PlainDateTime/withCalendar','withCalendar()')}}`
  - : Returns a `Temporal.PlainDateTime` object of the date and time projected
    into a specified calendar.
- `{{jsxref('Temporal/PlainDateTime/add','add()')}}`
  - : Creates a new `Temporal.PlainDateTime` object by adding a duration to the
    date and time.
- `{{jsxref('Temporal/PlainDateTime/subtract','subtract()')}}`
  - : Creates a new `Temporal.PlainDateTime` object by subtracting a duration
    from the date and time.
- `{{jsxref('Temporal/PlainDateTime/until','until()')}}`
  - : Computes the elapsed time between the `Temporal.PlainDateTime` object and
    another date and time in the future, optionally rounds it, and returns it as
    a `{{jsxref('Temporal.Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/PlainDateTime/since','since()')}}`
  - : Computes the elapsed time between the `Temporal.PlainDateTime` object and
    another date and time in the past, optionally rounds it, and returns it as a
    `{{jsxref('Temporal.Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/PlainDateTime/round','round()')}}`
  - : Creates a new `Temporal.PlainDateTime` object by rounding the date and
    time.
- `{{jsxref('Temporal/PlainDateTime/equals','equals()')}}`
  - : Determines whether the date and time is exactly the same as another date
    and time.
- `{{jsxref('Temporal/PlainDateTime/toZonedDateTime','toZonedDateTime()')}}`
  - : Converts a `Temporal.PlainDateTime` object into a
    `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
    object.
- `{{jsxref('Temporal/PlainDateTime/toPlainDate','toPlainDate()')}}`
  - : Converts the date and time to a new
    `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
    object corresponding to the date portion of the original date and time.
- `{{jsxref('Temporal/PlainDateTime/toPlainYearMonth','toPlainYearMonth()')}}`
  - : Converts a `Temporal.PlainDateTime` object into a
    `{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
    object.
- `{{jsxref('Temporal/PlainDateTime/toPlainMonthDay','toPlainMonthDay()')}}`
  - : Converts a `Temporal.PlainDateTime` object into a
    `{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`
    object.
- `{{jsxref('Temporal/PlainDateTime/toPlainTime','toPlainTime()')}}`
  - : Converts the date and time to a new
    `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
    object corresponding to the time portion of the original date and time.
- `{{jsxref('Temporal/PlainDateTime/toLocaleString','toLocaleString()')}}`
  - : Returns a human-readable, language-sensitive representation of the date
    and time.
- `{{jsxref('Temporal/PlainDateTime/toString','toString()')}}`
  - : Returns a string representing the date and time in ISO 8601 format.
- `{{jsxref('Temporal/PlainDateTime/toJSON','toJSON()')}}`
  - : Returns a string representing the date and time in ISO 8601 format.
- `{{jsxref('Temporal/PlainDateTime/getISOFields','getISOFields()')}}`
  - : Returns an object containing the ISO 8601 calendar fields and values
    corresponding to the date and time.
- `{{jsxref('Temporal/PlainDateTime/valueOf','valueOf()')}}`
  - : Overrides
    {{jsxref('Object/valueOf','Object.prototype.valueOf')}} and
    **always** throws an exception.
