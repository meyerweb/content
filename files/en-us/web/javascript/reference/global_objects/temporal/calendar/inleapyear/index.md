---
title: Temporal.Calendar.prototype.inLeapYear()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/inLeapYear
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

The **`inLeapYear()`** method returns a boolean that indicates whether the
supplied date occurs in a leap year or not, as determined by the calendar system
associated with that date.

This method is called indirectly when reading the `inLeapYear` properties of the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}},
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}},
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}},
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}},
and
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
classes. It is thus rare for developers to need to call
`Temporal.Calendar.inLeapYear()` directly.

## Syntax

```js
inLeapYear(date);
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

A boolean indicating whether the supplied date occurs in a leap year as
determined by the date's calendar system.

## Examples

```js
const date = Temporal.PlainDate.from('2020-04-20').withCalendar('iso8601');
date.inLeapYear; // => true
date.calendar.inLeapYear(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date2.inLeapYear; // => false
date2.calendar.inLeapYear(date2); // same result, but calling the method directly

const date3 = Temporal.PlainDate.from('2022-04-20').withCalendar('iso8601');
date3.inLeapYear; // => false
date3.calendar.inLeapYear(date3); // same result, but calling the method directly

const date4 = Temporal.PlainDate.from('2022-04-20').withCalendar('hebrew');
date4.inLeapYear; // => true
date4.calendar.inLeapYear(date4); // same result, but calling the method directly
```
