---
title: Temporal.PlainYearMonth.prototype.add()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/add
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

The **`add()`** method creates a new
{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
object by adding a duration to a
{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
object.Adding a negative duration is equivalent to
{{jsxref('Temporal.PlainYearMonth/subtract','subtracting','','nocode')}}
the absolute value of that duration.

## Syntax

```js
add(duration)
add(duration, options)
```

### Parameters

- `duration`
  - : An object with properties denoting a duration, such as `{ months: 5 }`, or
    a string value such as `P5M`, or a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object.
    If `duration` is not such a string nor a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object,
    then it will be converted to one as if it were passed to
    {{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}.
- `options` {{optional_inline}}

  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainYearMonth` object. These are:

    - `overflow`
      - : Determines how out-of-range values in _duration_ are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'` \* : Out-of-range values will cause the function to throw a
          `RangeError`.
          > **Note:** The `overflow` option has no effect in the default ISO
          > calendar, because a year is always 12 months and therefore not
          > ambiguous. However, `overflow` may have an effect in calendars where
          > years can be different numbers of months.

    ### Return value

    A new
    {{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
    object representing the month indicated by `oldMonth` plus `duration`. If
    the result is earlier or later than the range that
    {{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
    can represent (just over half a million years centered on the Unix epoch), a
    `RangeError` will be thrown instead.

    ## Examples

    ```js
        ym = Temporal.PlainYearMonth.from('2019-06');
        ym.add({ years: 20, months: 4 }); // => 2039-10
        ```
