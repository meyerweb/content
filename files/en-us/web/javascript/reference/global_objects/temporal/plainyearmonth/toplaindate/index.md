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

The **`toPlainDate()`** method converts a
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
object into a
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object,
by supplying a day to be used with the year and month of the original
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}.

## Syntax

```js
toPlainDate(day)
```

### Parameters

- `day`
  - : An object representing a valid day of the month to be used in constructing
    the {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    via one property:
    - `day`
      - : An integer representing a valid day of the month. If the value is out
        of range for the month, a `RangeError` will be thrown.

### Return value

A {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
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
