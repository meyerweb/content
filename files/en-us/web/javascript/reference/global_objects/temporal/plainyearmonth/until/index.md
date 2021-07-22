---
title: Temporal.PlainYearMonth.prototype.until()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/until
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

The **`until()`** method computes the elapsed time from the month represented by
`yearMonth` until the another month, optionally rounds it, and returns it as a
{{jsxref('Temporal/Duration','Temporal.Duration')}} object.If
the second month is earlier than the first, then the resulting duration will be
negative. This method is similar to
{{jsxref('Temporal.PlainYearMonth/since','Temporal.PlainYearMonth.since()')}},
but reversed.

## Syntax

```js
until(otherYearMonth)
until(otherYearMonth, options)
```

### Parameters

- `otherYearMonth`
  - : Another month as either a
    {{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainYearMonth.from()','Temporal.PlainYearMonth.from()')}}.
- `options` {{optional_inline}}

  - : An object with properties defining how the rounding operation should be
    carried out. The allowed properties are:

    - `largestUnit`

      - : A string defining the largest unit of time allowed in the returned
        object. Valid values are:

        - `'auto'` (default)
        - `'years'`
        - `'months'` The `largestUnit` option controls how the resulting
          duration is expressed. A value of `'auto'` means `'years'`.

        The returned
        {{jsxref('Temporal/Duration','Temporal.Duration')}}
        object will not have any nonzero fields that are larger than the unit in
        `largestUnit`. A difference of one year and two months will become 14
        months when `largestUnit` is `'months'`, for example. However, a
        difference of one month will still be one month even if `largestUnit` is
        `'years'`.

        > **Note:** Unlike other Temporal types, weeks and lower are not allowed
        > for either `largestUnit` or `smallestUnit`, because the data model of
        > `Temporal.PlainYearMonth` doesn't have that accuracy. If you need to
        > calculate the difference between two `PlainYearMonth` objects in days,
        > convert them to
        > {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
        > objects and use
        > {{jsxref('Temporal.PlainDate/until','Temporal.PlainDate.until()')}}
        > instead.

    - `smallestUnit`
      - : A string defining the smallest unit of time allowed in the returned
        object. Valid values are the same as for `largestUnit`.
    - `roundingIncrement`
      - : An integer defining the granularity of the rounding of the unit given
        by `smallestUnit`. The default is `1`.
    - `roundingMode`

      - : A string defining how to deal with any remainders. If `roundingMode`
        is not defined, then no rounding will be performed. The valid values
        are:

        - `'ceil'`
          - : Always round up, toward the end of time.
        - `'floor'`

          `'trunc'` (default)

          - : Always round down, toward the beginning of time. These two
            rounding modes behave identically, but are included for consistency
            with
            {{jsxref('Temporal/Duration.round()','Temporal.Duration.round()')}},
            where they do **not** behave identically.

        - `'halfExpand'`
          - : Round to the nearest of the values allowed by `roundingIncrement`
            and `smallestUnit`. If there is a tie, round up, toward the end of
            time.

### Return value

A new {{jsxref('Temporal/Duration','Temporal.Duration')}}
object representing the difference between `yearMonth` and _otherYearMonth_.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2006-08');
other = Temporal.PlainYearMonth.from('2019-06');
ym.until(other);                            // => P12Y10M
ym.until(other, { largestUnit: 'months' }); // => P154M
other.until(ym, { largestUnit: 'months' }); // => -P154M
```
