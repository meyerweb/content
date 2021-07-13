---
title: Temporal.PlainYearMonth.prototype.toPlainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/toPlainDate
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainDate()</code></strong> method converts a <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> object into a <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object</span>, by supplying a day to be used with the year and month of the original <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code>.</p>

## Syntax

```js
toPlainDate(day)
```

### Parameters

- `day`
  - : An object representing a valid day of the month to be used in constructing
    the
    `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
    via one property:
    - `day`
      - : An integer representing a valid day of the month. If the value is out
        of range for the month, a `RangeError` will be thrown.

### Return value

A `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
object that represents the new calendar date.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2021-04');
ym.toPlainDate({ day: 23 }); // => 2021-04-23
```

```js
ym = Temporal.PlainYearMonth.from('2021-04');
ym.toPlainDate({ day: 37 });
  // => Uncaught RangeError: value out of range: 1 <= 37 <= 30
```
