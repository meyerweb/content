---
title: Temporal.Calendar.prototype.dateUntil()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/dateUntil
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

The **`dateUntil()`** method provides a way to find the span of time between two
datetimes in the calendar's reckoning.This method does not need to be called
directly except in specialized code. It is called indirectly when using the
`until()` and `since()` methods of the
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}},
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}, and
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
classes, and from a number of other methods.

## Syntax

```js
dateUntil(date1, date2);
dateUntil(date1, date2, options);
```

### Parameters

- `date1`
  - : A date. If this is not a
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    object, it will be converted to one as if passed to
    {{jsxref('Temporal.PlainDate.from()','Temporal.PlainDate.from()')}}.
- `date2`
  - : Another date. If this is not a
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    object, it will be converted to one as if passed to
    {{jsxref('Temporal.PlainDate.from()','Temporal.PlainDate.from()')}}.
- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new Temporal object. These are:
    - `largestUnit`
      - : The largest unit of time to allow in the resulting
        {{jsxref('Temporal.Duration','Temporal.Duration')}}
        object. Valid values are `auto`, `years`, `months`, and `days`. The
        default is `auto`, which is treated the same as `days`.

### Return value

A new {{jsxref('Temporal/Duration','Temporal.Duration')}}
object representing the elapsed time between _date1_ and _date2_. If _date1_ is
later than _date2_, the resulting duration should be negative.

## Examples

```js
date = Temporal.Calendar.from('chinese').dateUntil(
  Temporal.PlainDate.from('2021-02-23'),
  Temporal.PlainDate.from('2021-04-20'),
  { largestUnit: 'months' }
); // => "P1M3W6D"
```
