---
title: Temporal.Calendar.prototype.daysInMonth()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/daysInMonth
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>daysInMonth()</code></strong> method returns the number of days in the month in which the supplied date occurs, as determined by the calendar system associated with that date.</span></p>

This method is called indirectly when reading the `daysInMonth` properties of
the
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`,
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`,
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`,
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`,
and
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
classes. It is thus rare for developers to need to call
`Temporal.Calendar.daysInMonth()` directly.

## Syntax

```js
daysInMonth(date);
```

### Parameters

- `date`
  - : The _date_ parameter can be one of the following Temporal objects:
    - `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
    - `{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
    - `{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
    - `{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
      If the parameter's value is not one of those objects, it will be converted
      to a
      `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
      as if it were passed to
      `{{jsxref('Temporal.PlainDate.from()','Temporal.PlainDate.from()')}}`.

### Return value

A number representing the days in the date's month as determined by the date's
calendar system.

## Examples

```js
const date = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date.daysInMonth; // => 30
date.calendar.daysInMonth(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('islamic');
date2.daysInMonth; // => 29
date2.calendar.daysInMonth(date2); // same result, but calling the method directly
```
