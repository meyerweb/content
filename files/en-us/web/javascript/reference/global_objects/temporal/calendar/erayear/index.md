---
title: Temporal.Calendar.prototype.eraYear()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/eraYear
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

The **`eraYear()`** method returns the year within the era of the supplied date,
as determined by the calendar system associated with that date, assuming the
calendar system uses eras.

This method is called indirectly when reading the `eraYear` properties of the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}},
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}},
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}},
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}},
and
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
classes. It is thus rare for developers to need to call
`Temporal.Calendar.eraYear()` directly.

## Syntax

```js
eraYear(date);
```

### Parameters

- `date`
  - : The _date_ parameter can be one of the following Temporal objects:
    - {{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
    - {{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
    - {{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
    - {{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
      If the parameter's value is not one of those objects, it will be converted
      to a
      {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
      as if it were passed to
      {{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}.

### Return value

A number representing the date's year within its era as determined by the date's
calendar system, or `undefined` if there is no era associated with the date.

## Examples

```js
date = Temporal.Calendar.from('gregory').dateFromFields(
  { year: 2021, month: 4, day: 20 }
);
date.eraYear; // => 2021
```
