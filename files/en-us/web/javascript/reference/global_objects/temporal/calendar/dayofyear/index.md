---
title: Temporal.Calendar.prototype.dayOfYear()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/dayOfYear
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>dayOfYear()</code></strong> method returns the day of the year of the supplied date, as determined by the calendar system associated with that date.</span></p>

This method is called indirectly when reading the `dayOfYear` properties of the
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`,
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`,
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`,
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`,
and
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
classes. It is thus rare for developers to need to call
`Temporal.Calendar.dayOfYear()` directly.

## Syntax

```js
dayOfYear(date);
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

A number representing the date's day of the year as determined by the date's
calendar system.

## Examples

```js
const date = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date.dayOfYear; // => 110
date.calendar.dayOfYear(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('islamic');
date2.dayOfYear; // => 112
date2.calendar.dayOfYear(date2); // same result, but calling the method directly
```
