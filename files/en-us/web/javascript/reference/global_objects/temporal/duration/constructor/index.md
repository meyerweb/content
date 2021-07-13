---
title: Temporal.Duration constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/constructor
tags:
  - Class
  - JavaScript
  - Time
  - constructor
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The constructor for a <code>{{jsxref('Temporal/Duration','Temporal.Duration')}}</code> object.</span> Use this constructor directly if you have the correct parameters already as numerical values. Otherwise, the <code>{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}</code> method is preferred, because it accepts more kinds of input and provides options for handling overflow.</p>

## Syntax

```js
new Temporal.Duration(years, months, weeks, days, hours, minutes, seconds, milliseconds, microseconds, nanoseconds)
```

### Parameters

All parameters are {{optional_inline}} and specified as integers. Any
missing or `undefined` numerical arguments are taken to be zero. Any non-integer
numerical value is truncated to the nearest integer, towards zero. Non-zero
values must all have the same sign.

- `years` – A number of years.
- `months` – A number of months.
- `weeks` – A number of weeks.
- `days` – A number of days.
- `hours` – A number of hours.
- `minutes` – A number of minutes.
- `seconds` – A number of seconds.
- `milliseconds` – A number of milliseconds.
- `microseconds` – A number of microseconds.
- `nanoseconds` – A number of nanoseconds.

### Return value

A new `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
object.

## Examples

```js
new Temporal.Duration(1, 2, 3, 4, 5, 6, 7, 987, 654, 321); // => P1Y2M3W4DT5H6M7.987654321S
new Temporal.Duration(0, 0, 0, 40); // => P40D
new Temporal.Duration(undefined, undefined, undefined, 40); // => P40D
new Temporal.Duration(); // => PT0S
```
