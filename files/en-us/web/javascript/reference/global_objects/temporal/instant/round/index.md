---
title: Temporal.Instant.prototype.round()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/round
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
{{jsxref('Temporal/Instant','Temporal.Instant')}} object by
rounding the current
{{jsxref('Temporal/Instant','Temporal.Instant')}}.

## Syntax

```js
round(options)
```

### Parameters

- `options`

  - : An object with properties defining how the rounding operation should be
    carried out. The allowed properties are:

    - `smallestUnit` (required)
      - : A string defining the unit of rounding. Valid values are:
        - `'hour'`
        - `'minute'`
        - `'second'`
        - `'millisecond'`
        - `'microsecond'`
        - `'nanosecond'`
    - `roundingIncrement`
      - : An integer defining the granularity of the rounding of the unit given
        by `smallestUnit`. The default is `1`.
    - `roundingMode`

      - : A string defining how to deal with any remainders. The valid values
        are:

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

A new {{jsxref('Temporal/Instant','Temporal.Instant')}} object
representing the exact time of `instant` as rounded according to the values
supplied in `options`.

## Examples

```js
instant = Temporal.Instant.from('2019-03-30T02:45:59.999999999Z');

// Round to a particular unit
instant.round({ smallestUnit: 'second' }); // => 2019-03-30T02:46Z

// Round to an increment of a unit, e.g. half an hour:
instant.round({ roundingIncrement: 30, smallestUnit: 'minute' });
// => 2019-03-30T03:00Z

// Round to the same increment but round down instead:
instant.round({ roundingIncrement: 30, smallestUnit: 'minute', roundingMode: 'floor' });
// => 2019-03-30T02:30Z
```
