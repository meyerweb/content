---
title: Temporal.Calendar.prototype.monthCode()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/monthCode
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>monthCode()</code></strong> method returns a string label for the month component of the supplied date, as determined by the calendar system associated with that date.</span> This is <strong>not</strong> the month's common name, such as "March", but instead a label for the month, such as "M03".</p>

This method is called indirectly when reading the `monthCode` properties of the
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`,
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`,
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`,
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`,
and
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
classes. It is thus rare for developers to need to call
`Temporal.Calendar.monthCode()` directly.

## Syntax

```js
monthCode(date);
```

### Parameters

- `date`
  - : The _date_ parameter can be one of the following Temporal objects:
    - `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
    - `{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
    - `{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
    - `{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
    - `{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}`
      If the parameter's value is not one of those objects, it will be converted
      to a
      `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
      as if it were passed to
      `{{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}`.

### Return value

A string representing the date's month code as determined by the date's calendar
system.

## Examples

```js
const date = Temporal.PlainDate.from('2021-04-20').withCalendar('iso8601');
date.monthCode; // => "M04"
date.calendar.monthCode(date); // same result, but calling the method directly

const date2 = Temporal.PlainDate.from('2021-04-20').withCalendar('islamic');
date2.monthCode; // => "M09"
date2.calendar.monthCode(date2); // same result, but calling the method directly
```
