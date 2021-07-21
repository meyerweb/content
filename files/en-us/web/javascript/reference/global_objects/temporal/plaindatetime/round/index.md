---
title: Temporal.PlainDateTime.prototype.round()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/round
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
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object by rounding a
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object.

## Syntax

```js
round(options)
```

### Parameters

- `options`

  - : An object with properties defining how the rounding operation should be
    carried out. The allowed properties are:

    - `smallestUnit`
      - : A string defining the unit to which the time should be rounded. Valid
        values are:
        - `'day'`
        - `'hour'`
        - `'minute'`
        - `'second'`
        - `'millisecond'`
        - `'microsecond'`
        - `'nanosecond'` This property is required, so there is no default
          value.
    - `roundingIncrement` {{ optional_inline }}

      - : An integer defining the granularity of the rounding of the unit given
        by `smallestUnit`. The default is `1`. If the value of `smallestUnit` is
        `'day'`, then the value of `roundingIncrement` must be `1`.

        `roundingIncrement` must divide evenly into the next highest unit after
        `smallestUnit`, and must not be equal to it. For example, if
        `smallestUnit` is `'minutes'`, then the number of minutes given by
        `roundingIncrement` must divide evenly into 60 minutes, which is one
        hour. The valid values in this case are 1 (default), 2, 3, 4, 5, 6, 10,
        12, 15, 20, and 30. (Instead of 60 minutes, use 1 hour.)

    - `roundingMode` {{ optional_inline }}

      - : A string defining how the rounding is conducted. The valid values are:

        - `'ceil'`
          - : Always round up, toward the end of time.
        - `'floor'`

          `'trunc'`

          - : Always round down, toward the beginning of time. These two
            rounding modes behave identically, but are included for consistency
            with
            {{jsxref('Temporal/Duration.round()','Temporal.Duration.round()')}},
            where they do **not** behave identically.

        - `'halfExpand'` (default)
          - : Round to the nearest of the values allowed by `roundingIncrement`
            and `smallestUnit`. If there is a tie, round up, toward the end of
            time.

### Return value

A new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object representing the rounded-off date and time.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');

// Round to a particular unit
dt.round({ smallestUnit: 'hour' }); // => 1995-12-07T03:00:00
// Round to an increment of a unit, e.g. half an hour:
dt.round({ roundingIncrement: 30, smallestUnit: 'minute' });
  // => 1995-12-07T03:30:00
// Round to the same increment but round down instead:
dt.round({ roundingIncrement: 30, smallestUnit: 'minute', roundingMode: 'floor' });
  // => 1995-12-07T03:00:00
```
