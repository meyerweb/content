---
title: Temporal.PlainDate
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate
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

<p class="summary"><span class="seoSummary">A <code>Temporal.PlainDate</code> represents a calendar date. "Calendar date" refers to the concept of a date as expressed in everyday usage, independent of any time zone.</span> For example, it could be used to represent an event on a calendar which happens during the whole day, no matter which time zone it's happening in, such as a national holiday.</p>

`Temporal.PlainDate` refers to the whole of a specific day; if you need to refer
to a specific time on that day, use
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`.

## Constructor

- `{{jsxref('Temporal/PlainDate/constructor','new Temporal.PlainDate()')}}`
  - : Creates a new `Temporal.PlainDate` object which represents a combination
    of year, month, and day.

## Instance Properties

- `{{jsxref('Temporal/PlainDate/year','year')}}`
  {{readonlyinline}}
  - : The year in which the date occurs.
- `{{jsxref('Temporal/PlainDate/month','month')}}`
  {{readonlyinline}}
  - : The number of the month in which the date occurs.
- `{{jsxref('Temporal/PlainDate/monthCode','monthCode')}}`
  {{readonlyinline}}
  - : A calendar-specific string identifying the date's month in a
    year-independent manner.
- `{{jsxref('Temporal/PlainDate/day','day')}}`
  {{readonlyinline}}
  - : The day of the month on which the date occurs.
- `{{jsxref('Temporal/PlainDate/calendar','calendar')}}`
  {{readonlyinline}}
  - : An object containing the calendar in which the
    `{{jsxref('Temporal/PlainDate/year','year')}}`,
    `{{jsxref('Temporal/PlainDate/month','month')}}`, and
    `{{jsxref('Temporal/PlainDate/day','day')}}` properties are
    interpreted.
- `{{jsxref('Temporal/PlainDate/era','era')}}`
  {{readonlyinline}}
  - : A string of the era in which the date occurs, in calendar systems that use
    eras.
- `{{jsxref('Temporal/PlainDate/eraYear','eraYear')}}`
  {{readonlyinline}}
  - : The year of the era in which the date occurs, in calendar systems that use
    eras.
- `{{jsxref('Temporal/PlainDate/dayOfWeek','dayOfWeek')}}`
  {{readonlyinline}}
  - : The weekday number on which the date falls.
- `{{jsxref('Temporal/PlainDate/dayOfYear','dayOfYear')}}`
  {{readonlyinline}}
  - : The ordinal day of the year on which the date falls.
- `{{jsxref('Temporal/PlainDate/weekOfYear','weekOfYear')}}`
  {{readonlyinline}}
  - : The ISO week number in which the date falls.
- `{{jsxref('Temporal/PlainDate/daysInWeek','daysInWeek')}}`
  {{readonlyinline}}
  - : The number of days in the week containing the date.
- `{{jsxref('Temporal/PlainDate/daysInMonth','daysInMonth')}}`
  {{readonlyinline}}
  - : The number of days in the month containing the date.
- `{{jsxref('Temporal/PlainDate/daysInYear','daysInYear')}}`
  {{readonlyinline}}
  - : The number of days in the year containing the date.
- `{{jsxref('Temporal/PlainDate/monthsInYear','monthsInYear')}}`
  {{readonlyinline}}
  - : The number of months in the year containing the date.
- `{{jsxref('Temporal/PlainDate/inLeapYear','inLeapYear')}}`
  {{readonlyinline}}
  - : Indicates whether the date occurs in a leap year.

## Static Methods

- `{{jsxref('Temporal/PlainDate/from','from()')}}`
  - : Creates a new `Temporal.PlainDate` object from another value.
- `{{jsxref('Temporal/PlainDate/compare','compare()')}}`
  - : Compares two dates and returns an integer indicating which comes before
    the other.

## Instance Methods

- `{{jsxref('Temporal/PlainDate/with','with()')}}`
  - : Returns a new `Temporal.PlainDate` object which is a modification of the
    original object using new property values.
- `{{jsxref('Temporal/PlainDate/withCalendar','withCalendar()')}}`
  - : Returns a `Temporal.PlainDate` object of a date projected into a specified
    calendar.
- `{{jsxref('Temporal/PlainDate/add','add()')}}`
  - : Creates a new `Temporal.PlainDate` object by adding a duration to the
    date.
- `{{jsxref('Temporal/PlainDate/subtract','subtract()')}}`
  - : Creates a new `Temporal.PlainDate` object by subtracting a duration from
    the date.
- `{{jsxref('Temporal/PlainDate/until','until()')}}`
  - : Computes the elapsed time from the date represented by the
    `Temporal.PlainDate` object until another date, optionally rounds it, and
    returns it as a
    `{{jsxref('Temporal.Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/PlainDate/since','since()')}}`
  - : Computes the elapsed time from the date between the `Temporal.PlainDate`
    object until another date in the past, optionally rounds it, and returns it
    as a `{{jsxref('Temporal.Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/PlainDate/equals','equals()')}}`
  - : Determines whether the date is exactly the same as another date.
- `{{jsxref('Temporal/PlainDate/toZonedDateTime','toZonedDateTime()')}}`
  - : Converts a `Temporal.PlainDate` object into a
    `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
    object.
- `{{jsxref('Temporal/PlainDate/toPlainDateTime','toPlainDateTime()')}}`
  - : Converts a `Temporal.PlainDate` object into a
    `{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`
    object.
- `{{jsxref('Temporal/PlainDate/toPlainYearMonth','toPlainYearMonth()')}}`
  - : Converts a `Temporal.PlainDate` object into a
    `{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
    object.
- `{{jsxref('Temporal/PlainDate/toPlainMonthDay','toPlainMonthDay()')}}`
  - : Converts a `Temporal.PlainDate` object into a
    `{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`
    object.
- `{{jsxref('Temporal/PlainDate/toLocaleString','toLocaleString()')}}`
  - : Returns a human-readable, language-sensitive representation of the date.
- `{{jsxref('Temporal/PlainDate/toString','toString()')}}`
  - : Returns a string representing the date in ISO 8601 format.
- `{{jsxref('Temporal/PlainDate/toJSON','toJSON()')}}`
  - : Returns a string representing the date in ISO 8601 format.
- `{{jsxref('Temporal/PlainDate/getISOFields','getISOFields()')}}`
  - : Returns an object containing the ISO 8601 calendar fields and values
    corresponding to the date.
- `{{jsxref('Temporal/PlainDate/valueOf','valueOf()')}}`
  - : Overrides
    {{jsxref('Object/valueOf','Object.prototype.valueOf')}} and
    **always** throws an exception.
