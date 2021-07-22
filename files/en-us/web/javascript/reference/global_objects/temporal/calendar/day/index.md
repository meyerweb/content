---
title: Temporal.Calendar.prototype.day()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/day
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

The **`day()`** method returns the day component of the supplied date, as
determined by the calendar system associated with that date.

This method is called indirectly when reading the `day` properties of the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}},
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}},
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}, and
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
classes. It is thus rare for developers to need to call
`Temporal.Calendar.day()` directly.

## Syntax

```js
day(date);
```

### Parameters

- `date`
  - : The _date_ parameter can be one of the following Temporal objects:
    - {{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
    - {{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
    - {{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
    - {{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}
      If the parameter's value is not one of those objects, it will be converted
      to a
      {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
      as if it were passed to
      {{jsxref('Temporal.PlainDate.from()','Temporal.PlainDate.from()')}}.

### Return value

A number representing the date's day as determined by the date's calendar
system.

## Examples

```js
const date = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date.day; // => 20
date.calendar.day(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('islamic');
date2.day; // => 8
date2.calendar.day(date2); // same result, but calling the method directly
```
