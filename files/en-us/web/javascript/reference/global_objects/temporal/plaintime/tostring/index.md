---
title: Temporal.PlainTime.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/toString
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`toString()`** method returns a string representing the wall-clock time in
ISO 8601 format.This method overrides the
{{jsxref('Object.toString','Object.prototype.toString()')}}
method and provides a convenient, unambiguous string representation of a
wall-clock time. The string can be passed to
{{jsxref('Temporal.PlainTime/from','Temporal.PlainTime.from()')}}
to create a new
{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}} object.

## Syntax

```js
toString();
toString(options)
```

### Parameters

- `options` {{optional_inline}}

  - : An object with properties influencing the formatting. The following
    options are recognized:

    - `fractionalSecondDigits`
      - : An single-digit integer or the string `'auto'` defining how many
        digits to print after the decimal point in the output string. The
        default is `'auto'`, which omits any trailing zeroes after the decimal
        point.
    - `smallestUnit`
      - : A string defining the smallest unit of time to include in the output
        string. Valid values are:
        - `'minute'`
        - `'second'`
        - `'millisecond'`
        - `'microsecond'`
        - `'nanosecond'`
          > **Note:** If `smallestUnit` is defined, it overrides the value of
          > `fractionalSecondDigits`.
    - `roundingMode`

      - : A string defining how to deal with any remainder. The valid values
        are:

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

A string representing the wall-clock time in ISO 8601 format.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.toString(); // => '19:39:09.068346205'
time.toString({ smallestUnit: 'minute' }); // => '19:39'
time.toString({ fractionalSecondDigits: 0 }); // => '19:39:09'
time.toString({ fractionalSecondDigits: 4 }); // => '19:39:09.0683'
time.toString({ fractionalSecondDigits: 5, roundingMode: 'halfExpand' });
  // => '19:39:09.06835'
```
