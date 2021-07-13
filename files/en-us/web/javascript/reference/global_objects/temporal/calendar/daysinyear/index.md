---
title: Temporal.Calendar.prototype.daysInYear()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/daysInYear
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>daysInYear()</code></strong> method returns the number of days in the year in which the supplied date occurs, as determined by the calendar system associated with that date.</span></p>

This method is called indirectly when reading the `daysInYear` properties of the
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`,
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`,
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`,
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`,
and
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
classes. It is thus rare for developers to need to call
`Temporal.Calendar.daysInYear()` directly.

## Syntax

```js
daysInYear(date);
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

A number representing the days in the date's year as determined by the date's
calendar system.

## Examples

```js
const date = Temporal.PlainDate.from('2020-04-20').withCalendar('iso8601');
date.daysInYear; // => 366, because 2020 is a leap year
date.calendar.daysInYear(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date2.daysInYear; // => 365, because 2021 is not a leap year
date2.calendar.daysInYear(date); // same result, but calling the method directly

const date3 = Temporal.PlainDate.from('2021-04-20').withCalendar('islamic');
date3.daysInYear; // => 354
date3.calendar.daysInYear(date2); // same result, but calling the method directly
```
