---
title: Temporal.PlainDate.prototype.since()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/since
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

The **`since()`** method computes the elapsed time between the date represented
by `plainDate` and another date in the past, optionally rounds it, and returns
it as a {{jsxref('Temporal/Duration','Temporal.Duration')}}
object.If the second date is later than the first, then the resulting duration
will be negative. This method is similar to
{{jsxref('Temporal.PlainDate/until','Temporal.PlainDate.until()')}},
but reversed.

> **Warning:** Computing the difference between dates in different calendar
> systems is not supported. If you need to do this, choose the calendar in which
> the computation takes place by converting one of the dates using the method
> {{jsxref('Temporal.PlainDate/withCalendar','withCalendar()')}}.

## Syntax

```js
since(otherDate)
since(otherDate, options)
```

### Parameters

- `otherDate`
  - : Another date as either a
    {{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainDate.from()','Temporal.PlainDate.from()')}}.
- `options` {{optional_inline}}

  - : An object with properties defining how the difference operation should be
    carried out. The allowed properties are:

    - `largestUnit`

      - : A string defining the largest unit of time allowed in the returned
        object. Valid values are:

        - `'auto'` (default)
        - `'years'`
        - `'months'`
        - `'weeks'`
        - `'days'` The `largestUnit` option controls how the resulting duration
          is expressed. A value of `'auto'` means to match the value of
          `smallestUnit`.

        The returned
        {{jsxref('Temporal/Duration','Temporal.Duration')}}
        object will not have any nonzero fields that are larger than the unit in
        `largestUnit`. A difference of one year and two months will become 14
        months when `largestUnit` is `'months'`, for example. However, a
        difference of one month will still be one month even if `largestUnit` is
        `'years'`.

        > **Note:** Unlike some other Temporal types, hours and lower are not
        > allowed for either `largestUnit` or `smallestUnit`, because the data
        > model of `Temporal.PlainDate` doesn't have that accuracy.

    - `smallestUnit`
      - : A string defining the smallest unit of time allowed in the returned
        object. Valid values are the same as for `largestUnit`, except the
        default value is `'days'`, which means no rounding will occur.
    - `roundingIncrement`
      - : An integer defining the granularity of the rounding of the unit given
        by `smallestUnit`. The default is `1`.
    - `roundingMode`

      - : A string defining how to deal with any remainders. The valid values
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
object representing the difference between the two dates.

## Examples

```js
earlier = Temporal.PlainDate.from('2006-08-24');
later = Temporal.PlainDate.from('2019-01-31');
later.since(earlier); // => P4543D
```
