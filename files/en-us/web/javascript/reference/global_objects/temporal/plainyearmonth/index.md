---
title: Temporal.PlainYearMonth
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth
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

<p class="summary"><span class="seoSummary">A <code>Temporal.PlainYearMonth</code> represents a particular month on the calendar. For example, it could be used to represent a particular instance of a monthly recurring event, like "the June 2019 meeting".</span></p>

`Temporal.PlainYearMonth` refers to the whole of a specific month; if you need
to refer to a calendar event on a certain day, use
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}` or
even
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`.
A `Temporal.PlainYearMonth` can be converted into a
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}` by
combining it with a day of the month, using the
`{{jsxref('Temporal.PlainYearMonth/toPlainDate','toPlainDate()')}}`
method.

## Constructor

- `new {{jsxref('Temporal/PlainYearMonth/constructor','Temporal.PlainYearMonth()')}}`
  - : Creates a new `Temporal.PlainYearMonth` object which represents a
    combination of year and month, with no associated single day.

## Instance Properties

- `{{jsxref('Temporal/PlainYearMonth/year','year')}}`
  {{readonlyinline}}
  - : A number that identifies the year in which the date occurs.
- `{{jsxref('Temporal/PlainYearMonth/month','month')}}`
  {{readonlyinline}}
  - : A number that identifies the month in which the date occurs.
- `{{jsxref('Temporal/PlainYearMonth/monthCode','monthCode')}}`
  {{readonlyinline}}
  - : A calendar-specific string that identifies the month in a year-independent
    manner.
- `{{jsxref('Temporal/PlainYearMonth/calendar','calendar')}}`
  {{readonlyinline}}
  - : An object containing the calendar in which the `year` and `month`
    properties are interpreted.
- `{{jsxref('Temporal/PlainYearMonth/era','era')}}`
  {{readonlyinline}}
  - : A string of the era in which the date occurs, in calendar systems that use
    eras.
- `{{jsxref('Temporal/PlainYearMonth/eraYear','eraYear')}}`
  {{readonlyinline}}
  - : A number identifying the era in which the date occurs, in calendar systems
    that use eras.
- `{{jsxref('Temporal/PlainYearMonth/daysInMonth','daysInMonth')}}`
  {{readonlyinline}}
  - : The number of days in the month.
- `{{jsxref('Temporal/PlainYearMonth/daysInYear','daysInYear')}}`
  {{readonlyinline}}
  - : The number of days in the year.
- `{{jsxref('Temporal/PlainYearMonth/monthsInYear','monthsInYear')}}`
  {{readonlyinline}}
  - : The number of months in the year.
- `{{jsxref('Temporal/PlainYearMonth/inLeapYear','inLeapYear')}}`
  {{readonlyinline}}
  - : A boolean indicating whether the date occurs in a leap year.

## Static Methods

- `{{jsxref('Temporal/PlainYearMonth/from','from()')}}`
  - : Creates a new `Temporal.PlainYearMonth` object from another value.
- `{{jsxref('Temporal/PlainYearMonth/compare','compare()')}}`
  - : Compares two dates and returns an integer indicating which comes before
    the other.

## Instance Methods

- `{{jsxref('Temporal/PlainYearMonth/with','with()')}}`
  - : Returns a new `Temporal.PlainYearMonth` object which is a modification of
    the original object with new property values.
- `{{jsxref('Temporal/PlainYearMonth/add','add()')}}`
  - : Creates a new `Temporal.PlainYearMonth` object by adding a span of time to
    a `Temporal.PlainYearMonth` object.
- `{{jsxref('Temporal/PlainYearMonth/subtract','subtract()')}}`
  - : Creates a new `Temporal.PlainYearMonth` object by subtracting a span of
    time from a `Temporal.PlainYearMonth` object.
- `{{jsxref('Temporal/PlainYearMonth/until','until()')}}`
  - : Computes the elapsed time between two `Temporal.PlainYearMonth`s,
    optionally rounds the result, and returns it as a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/PlainYearMonth/since','since()')}}`
  - : Computes the elapsed time between two `Temporal.PlainYearMonth`s,
    optionally rounds the result, and returns it as a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/PlainYearMonth/equals','equals()')}}`
  - : Determines whether a `Temporal.PlainYearMonth` object is exactly the same
    as another year-month combination.
- `{{jsxref('Temporal/PlainYearMonth/valueOf','valueOf()')}}`
  - : Overrides
    `{{jsxref('Object/valueOf','Object.prototype.valueOf')}}`.
    **Always** throws an exception.
- `{{jsxref('Temporal/PlainYearMonth/toPlainDate','toPlainDate()')}}`
  - : Converts a `Temporal.PlainYearMonth` object into a
    `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
    object.
- `{{jsxref('Temporal/PlainYearMonth/getISOFields','getISOFields()')}}`
  - : Returns an object containing the ISO 8601 calendar fields and values that
    correspond to the year and month.
- `{{jsxref('Temporal/PlainYearMonth/toLocaleString','toLocaleString()')}}`
  - : Returns a human-readable, language-sensitive representation of the
    `Temporal.PlainYearMonth` value.
- `{{jsxref('Temporal/PlainYearMonth/toString','toString()')}}`
  - : Returns a string representing the year and month in ISO 8601 format.
- `{{jsxref('Temporal/PlainYearMonth/toJSON','toJSON()')}}`
  - : Returns a string representing the year and month in ISO 8601 format.
