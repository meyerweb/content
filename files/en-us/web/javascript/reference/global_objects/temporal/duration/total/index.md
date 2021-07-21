---
title: Temporal.Duration.prototype.total()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/total
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

The **`total()`** method returns the number of instances of a particular time
unit equal to the
{{jsxref('Temporal/Duration','Temporal.Duration')}} object.If
the duration is not evenly divisible by the desired unit, then a fractional
remainder will be present in the result.

## Syntax

```js
total(options)
```

### Parameters

- `options`
  - : An object with properties defining how the totaling operation should be
    carried out. The allowed properties are:
    - `unit`
      - : A string defining the largest unit of time to allow in the totaled
        result. Valid values are:
        - `'years'`
        - `'months'`
        - `'weeks'`
        - `'days'`
        - `'hours'`
        - `'minutes'`
        - `'seconds'`
        - `'milliseconds'`
        - `'microseconds'`
        - `'nanoseconds'` This property is required, so there is no default
          value.
    - `relativeTo` {{optional_inline}}(see note)
      - : The starting point to use when converting between years, months,
        weeks, and days, expressed as a
        {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
        object, or else a value convertible to one.
        > **Warning:** If `unit` is `'years'`, `'months'`, or `'weeks'`, the
        > `relativeTo` option is **required**.

### Return value

A floating-point number representing the number of specified time units in the
{{jsxref('Temporal.Duration','Temporal.Duration')}} object.

## Examples

```js
// How many seconds in 18 hours and 20 minutes?
d = Temporal.Duration.from({ hours: 130, minutes: 20 });
d.total({ unit: 'seconds' }); // => 469200

// How many 24-hour days is 123456789 seconds?
d = Temporal.Duration.from('PT123456789S');
d.total({ unit: 'days' }); // 1428.8980208333332

// Find totals in months, with and without taking DST into account
d = Temporal.Duration.from({ hours: 2756 });
d.total({
   relativeTo: '2020-01-01T00:00+01:00[Europe/Rome]',
   unit: 'months'
}); // => 3.7958333333333334
d.total({
  unit: 'months',
  relativeTo: '2020-01-01'
}); // => 3.7944444444444443
```
