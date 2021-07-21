---
title: Temporal.PlainMonthDay
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay
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

A month-and-day object which is not associated with a specific year, even if a
specific year is used in its creation.It is useful to represent a yearly
recurring event, such as "our wedding anniversary is October 20th" or "Bastille
Day is on the 14th of July."

A `Temporal.PlainMonthDay` can be converted into a
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} by
combining it with a year, using the
{{jsxref('Temporal.PlainMonthDay/toPlainDate','Temporal.PlainMonthDay.toPlainDate()')}}
method. If you need to refer to a certain instance of a calendar event in a
particular year, use
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} or even
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
instead.

## Constructor

- {{jsxref('Temporal/PlainMonthDay/constructor','Temporal.PlainMonthDay()')}}
  - : Creates a new `Temporal.PlainMonthDay` object which represents a
    combination of month and day, with no associated year.

## Instance Properties

- {{jsxref('Temporal/PlainMonthDay/monthCode','monthCode')}}
  {{readonlyinline}}
  - : Returns a calendar-specific string that identifies the month in a
    year-independent manner.
- {{jsxref('Temporal/PlainMonthDay/day','day')}}
  {{readonlyinline}}
  - : Returns a number that identifies the day of the month on which the date
    occurs.
- {{jsxref('Temporal/PlainMonthDay/calendar','calendar')}}
  {{readonlyinline}}
  - : Returns an object containing the calendar in which the
    {{jsxref('Temporal/PlainMonthDay/monthCode','monthCode')}}
    and {{jsxref('Temporal/PlainMonthDay/day','day')}} properties
    are interpreted.

## Static Methods

- {{jsxref('Temporal/PlainMonthDay/from','from()')}}
  - : Creates a new `Temporal.PlainMonthDay` object from another value.

## Instance Methods

- {{jsxref('Temporal/PlainMonthDay/with','with()')}}
  - : Returns a new `Temporal.PlainMonthDay` object which is a modification of
    the original object with new property values.
- {{jsxref('Temporal/PlainMonthDay/equals','equals()')}}
  - : Compares two `Temporal.PlainMonthDay` objects to determine if they are the
    same.
- {{jsxref('Temporal/PlainMonthDay/valueOf','valueOf()')}}
  - : Overrides
    {{jsxref('Object/valueOf','Object.prototype.valueOf()')}}
    and **always** throws an exception.
- {{jsxref('Temporal/PlainMonthDay/toPlainDate','toPlainDate()')}}
  - : Converts a `Temporal.PlainMonthDay` object into a
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    object.
- {{jsxref('Temporal/PlainMonthDay/getISOFields','getISOFields()')}}
  - : Returns an object containing the ISO 8601 calendar fields and values that
    correspond to the month and day.
- {{jsxref('Temporal/PlainMonthDay/toLocaleString','toLocaleString()')}}
  - : Returns a language-sensitive representation of the month and day.
- {{jsxref('Temporal/PlainMonthDay/toString','toString()')}}
  - : Returns a string representing the month and day in ISO 8601 format.
- {{jsxref('Temporal/PlainMonthDay/toJSON','toJSON()')}}
  - : Returns a string representing the month and day in ISO 8601 format.
