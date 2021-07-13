---
title: Temporal.Calendar.prototype.year()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/year
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>year()</code></strong> method returns the year component of the supplied date, as determined by the calendar system associated with that date.</span></p>

This method is called indirectly when reading the `year` properties of the
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`,
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`,
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`, and
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
classes. It is thus rare for developers to need to call
`Temporal.Calendar.year()` directly.

## Syntax

```js
year(date);
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

A number representing the date's year as determined by the date's calendar
system.

## Examples

```js
const date = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date.year; // => 2021
date.calendar.year(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('islamic');
date2.year; // => 1442
date2.calendar.year(date2); // same result, but calling the method directly
```
