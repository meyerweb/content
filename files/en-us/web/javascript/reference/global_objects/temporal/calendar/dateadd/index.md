---
title: Temporal.Calendar.prototype.dateAdd()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/dateAdd
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>dateAdd()</code></strong> method provides a way to do date arithmetic in the calendar's reckoning.</span> This method does not need to be called directly except in specialized code. It is called indirectly when using the <code>add()</code> and <code>subtract()</code> methods of the <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code>, <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code>, and <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> classes.</p>

## Syntax

```js
dateAdd(date, duration);
dateAdd(date, duration, options);
```

### Parameters

- `date`
  - : The date to start from. If this is not a
    `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
    object, it will be converted to one as if passed to
    `{{jsxref('Temporal.PlainDate.from()','Temporal.PlainDate.from()')}}`.
- `duration`
  - : A duration (amount of time) to add to the value of _date_. If this is not
    a `{{jsxref('Temporal.Duration','Temporal.Duration')}}`
    object, it will be converted to one as if passed to
    `{{jsxref('Temporal.Duration.from()','Temporal.Duration.from()')}}`.
    To subtract, negative duration values are used.
- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new Temporal object. These are:
    - `overflow`
      - : Determines how out-of-range values in _date_ are handled. There are
        two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'`
          - : Out-of-range values will cause the function to throw a
            `RangeError`.

### Return value

A new
`{{jsxref('Temporal/plainYearMonth','Temporal.plainYearMonth')}}`
object representing the new year and month.

## Examples

```js
date = Temporal.Calendar.from('islamic').dateAdd(
  Temporal.PlainDate.from('2021-04-20'),
  Temporal.Duration.from({ months: 1 }),
  { overflow: 'reject' }
);
date.year; // => 1442
date.month; // => 10
date.day; // => 8
date.toString(); // => "2021-05-19[u-ca=islamic]"
```
