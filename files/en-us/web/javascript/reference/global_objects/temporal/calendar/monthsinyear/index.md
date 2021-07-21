---
title: Temporal.Calendar.prototype.monthsInYear()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/monthsInYear
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

The **`monthsInYear()`** method returns the number of months in the year in
which the supplied date occurs, as determined by the calendar system associated
with that date.

This method is called indirectly when reading the `monthsInYear` properties of
the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}},
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}},
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}},
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}},
and
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
classes. It is thus rare for developers to need to call
`Temporal.Calendar.monthsInYear()` directly.

## Syntax

```js
monthsInYear(date);
```

### Parameters

- `date`
  - : The _date_ parameter can be one of the following Temporal objects:
    - {{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
    - {{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
    - {{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
    - {{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
      If the parameter's value is not one of those objects, it will be converted
      to a
      {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
      as if it were passed to
      {{jsxref('Temporal.PlainDate.from()','Temporal.PlainDate.from()')}}.

### Return value

A number representing the months in the date's year as determined by the date's
calendar system.

## Examples

```js
const date = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date.monthsInYear; // => 12
date.calendar.monthsInYear(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('hebrew');
date2.monthsInYear; // => 12
date2.calendar.monthsInYear(date2); // same result, but calling the method directly

const date3 = Temporal.PlainDate.from('2022-04-20').withCalendar('hebrew');
date3.monthsInYear; // => 13
date3.calendar.monthsInYear(date3); // same result, but calling the method directly
```
