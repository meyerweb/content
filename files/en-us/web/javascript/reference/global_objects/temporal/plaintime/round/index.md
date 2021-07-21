---
title: Temporal.PlainTime.prototype.round()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/round
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

The **`round()`** method creates a new
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}} object
by rounding a
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}} object.

## Syntax

```js
round()
round(options)
```

### Parameters

- `options` {{optional_inline}}

  - : An object with properties defining how the rounding operation should be
    carried out. The allowed properties are:

    - `smallestUnit`
      - : A string defining the unit to which the time should be rounded. Valid
        values are:
        - `'auto'`
        - `'hours'`
        - `'minutes'`
        - `'seconds'`
        - `'milliseconds'`
        - `'microseconds'`
        - `'nanoseconds'` This property is required, so there is no default
          value.
    - `roundingIncrement` {{ optional_inline }}
      - : An integer defining the granularity of the rounding of the unit given
        by `smallestUnit`. The default is `1`. This value must divide evenly
        into the next highest unit after `smallestUnit`, and must not be equal
        to it. For example, if `smallestUnit` is `'minutes'`, then the number of
        minutes given by `roundingIncrement` must divide evenly into 60 minutes,
        which is one hour. The valid values in this case are 1 (default), 2, 3,
        4, 5, 6, 10, 12, 15, 20, and 30. Instead of 60 minutes, use 1 hour.)
    - `roundingMode` {{ optional_inline }}

      - : A string defining how the rounding is conducted. The valid values are:

        - `'ceil'`
          - : Always round up, toward 23:59:59.999999999.
        - `'floor'`

          `'trunc'`

          - : Always round down, toward 00:00. These two rounding modes behave
            identically, but are included for consistency with
            {{jsxref('Temporal/Duration.round()','Temporal.Duration.round()')}},
            where they do **not** behave identically.

        - `'halfExpand'` (default)
          - : Round to the nearest of the values allowed by `roundingIncrement`
            and `smallestUnit`. If there is a tie, round up, toward
            23:59:59.999999999.

### Return value

A new {{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}
object representing the rounded-off wall-clock time.

## Examples

```js
// Round to a particular unit
time.round({ smallestUnit: 'hour' }); // => 20:00:00
// Round to an increment of a unit, e.g. half an hour:
time.round({ roundingIncrement: 30, smallestUnit: 'minute' });
  // => 19:30:00
// Round to the same increment but round up instead:
time.round({ roundingIncrement: 30, smallestUnit: 'minute', roundingMode: 'ceil' });
  // => 20:00:00
```
