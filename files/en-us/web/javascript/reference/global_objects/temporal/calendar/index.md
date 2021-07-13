---
title: Temporal.Calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Calendar
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>Temporal.Calendar</code></strong> class provides an interface to represent a calendar system. A calendar system includes information about how many days are in each year, how many months are in each year, how many days are in each month, and how to do arithmetic in that system.</span></p>

On the modern Internet, the most often used calendar system is the calendar
standardized by [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601), which is the
same as the Gregorian calendar with the addition of week-numbering rules and the
removal of eras. In general it is extended backwards ("proleptically") to cover
the period of history before its invention, which is an optional modification
allowed by the ISO 8601 standard.

However, the ISO 8601 calendar is not the only calendar in common use in the
world. Some places use another calendar system as the main calendar, or have a
separate calendar system as a commonly-used civil or religious calendar.

## Constructor

- `{{jsxref('Temporal/Calendar/constructor','Temporal.Calendar()')}}`
  - : Creates a new `Temporal.Calendar` object which represents a calendar
    system.

## Instance Properties

- `{{jsxref('Temporal/Calendar/id','id')}}`
  {{readonlyinline}}
  - : Returns an unambigious identifier from a `Temporal.Calendar` object.

## Static Methods

- `{{jsxref('Temporal/Calendar/from','from()')}}`
  - : Creates a new
    `{{jsxref('Temporal/Calendar','Temporal.Calendar')}}`
    object from another value.

## Instance Methods

- `{{jsxref('Temporal/Calendar/era','era()')}}`
  - : Returns the era component of the supplied date, assuming the calendar
    system uses eras.
- `{{jsxref('Temporal/Calendar/eraYear','eraYear()')}}`
  - : Returns the year component of the supplied date within its era, assuming
    the calendar system uses eras.
- `{{jsxref('Temporal/Calendar/year','year()')}}`
  - : Returns the year component of the supplied date.
- `{{jsxref('Temporal/Calendar/month','month()')}}`
  - : Returns the month component of the supplied date.
- `{{jsxref('Temporal/Calendar/monthCode','monthCode()')}}`
  - : Returns the month code of the supplied date.
- `{{jsxref('Temporal/Calendar/day','day()')}}`
  - : Returns the day component of the supplied date.
- `{{jsxref('Temporal/Calendar/dayOfWeek','dayOfWeek()')}}`
  - : Returns the day-of-week component of the supplied date.
- `{{jsxref('Temporal/Calendar/dayOfYear','dayOfYear()')}}`
  - : Returns the day of the year of the supplied date.
- `{{jsxref('Temporal/Calendar/weekOfYear','weekOfYear()')}}`
  - : Returns the week number of the year of the supplied date.
- `{{jsxref('Temporal/Calendar/daysInWeek','daysInWeek()')}}`
  - : Returns the number of days in the week in which the supplied date occurs.
- `{{jsxref('Temporal/Calendar/daysInMonth','daysInMonth()')}}`
  - : Returns the number of days in the month in which the supplied date occurs.
- `{{jsxref('Temporal/Calendar/daysInYear','daysInYear()')}}`
  - : Returns the number of days in the year in which the supplied date occurs.
- `{{jsxref('Temporal/Calendar/monthsInYear','monthsInYear()')}}`
  - : Returns the number of months in the year in which the supplied date
    occurs.
- `{{jsxref('Temporal/Calendar/inLeapYear','inLeapYear()')}}`
  - : Returns a boolean that indicates whether the supplied date occurs in a
    leap year.
- `{{jsxref('Temporal/Calendar/dateFromFields','dateFromFields()')}}`
  - : Returns a new
    `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
    object determined by the field values passed to it.
- `{{jsxref('Temporal/Calendar/yearMonthFromFields','yearMonthFromFields()')}}`
  - : Returns a new
    `{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
    object determined by the field values passed to it.
- `{{jsxref('Temporal/Calendar/monthDayFromFields','monthDayFromFields()')}}`
  - : Returns a new
    `{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`
    object determined by the field values passed to it.
- `{{jsxref('Temporal/Calendar/dateAdd','dateAdd()')}}`
  - : Provides a way to do date arithmetic in the calendar's reckoning.
- `{{jsxref('Temporal/Calendar/dateUntil','dateUntil()')}}`
  - : Provides a way to find the span of time between two datetimes in the
    calendar's reckoning.
- `{{jsxref('Temporal/Calendar/fields','fields()')}}`
  - : Accepts an array of field names and returns an array fields that are
    strongly associated with the original array of fields in the current
    calendar.
- `{{jsxref('Temporal/Calendar/mergeFields','mergeFields()')}}`
  - : Combines two sets of properties, resolves any conflicts between the two,
    removes properties that are invalidated by the conflict resolution, and
    returns the result.
- `{{jsxref('Temporal/Calendar/toString','toString()')}}`
  - : Returns a string containing the value of the calendar's
    `{{jsxref('Temporal/Calendar/id','id')}}` property.
- `{{jsxref('Temporal/Calendar/toJSON','toJSON()')}}`
  - : Returns a string containing the value of the calendar's
    `{{jsxref('Temporal/Calendar/id','id')}}` property.
