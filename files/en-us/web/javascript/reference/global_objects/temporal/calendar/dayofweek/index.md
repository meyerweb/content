---
title: Temporal.Calendar.prototype.dayOfWeek()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/dayOfWeek
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>dayOfWeek()</code></strong> method returns the day-of-week component of the supplied date, as determined by the calendar system associated with that date.</span></p>

This method is called indirectly when reading the `dayOfWeek` properties of the
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`,
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`,
and `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
classes. It is thus rare for developers to need to call
`Temporal.Calendar.dayOfWeek()` directly.

Note that the number of a given day of the week is determined by the calendar
system; for example, the ISO 8601 calendar defines the days of the week as a
value of 1 to 7 inclusive, with Monday being 1, and Sunday 7.

## Syntax

```js
dayOfWeek(date);
```

### Parameters

- `date`
  - : The _date_ parameter can be one of the following Temporal objects:
    - `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
    - `{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
    - `{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
      If the parameter's value is not one of those objects, it will be converted
      to a
      `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
      as if it were passed to
      `{{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}`.

### Return value

A number representing the date's day as determined by the date's calendar
system.

## Examples

```js
const date = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date.dayOfWeek; // => 2
date.calendar.dayOfWeek(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('islamic');
date2.dayOfWeek; // => 2
date2.calendar.dayOfWeek(date2); // same result, but calling the method directly
```
