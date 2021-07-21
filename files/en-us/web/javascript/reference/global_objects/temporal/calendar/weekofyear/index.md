---
title: Temporal.Calendar.prototype.weekOfYear()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/weekOfYear
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

The **`weekOfYear()`** method returns the week number of the year of the
supplied date, as determined by the calendar system associated with that date.

This method is called indirectly when reading the `weekOfYear` properties of the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}},
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}},
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}},
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}},
and
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
classes. It is thus rare for developers to need to call
`Temporal.Calendar.weekOfYear()` directly.

## Syntax

```js
weekOfYear(date);
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

A number representing the date's week of the year as determined by the date's
calendar system.

## Examples

```js
const date = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date.weekOfYear; // => 16
date.calendar.weekOfYear(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('islamic');
date2.weekOfYear; // => 16
date2.calendar.weekOfYear(date2); // same result, but calling the method directly
```
