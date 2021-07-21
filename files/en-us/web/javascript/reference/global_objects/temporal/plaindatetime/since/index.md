---
title: Temporal.PlainDateTime.prototype.since()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/since
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

The **`since()`** method computes the elapsed time between the date and time
represented by _dateTime_ and another date and time in the past, optionally
rounds it, and returns it as a
{{jsxref('Temporal/Duration','Temporal.Duration')}} object.If
the second date and time is later than the first, then the resulting duration
will be negative. This method is similar to
{{jsxref('Temporal.PlainDateTime/until','Temporal.PlainDateTime.until()')}},
but reversed.

> **Warning:** Computing the difference between dates and times in different
> calendar systems is not supported. If you need to do this, choose the calendar
> in which the computation takes place by converting one of the dates and times
> using the method
> {{jsxref('Temporal.PlainDateTime/withCalendar','withCalendar()')}}.

## Syntax

```js
since(otherDateTime)
since(otherDateTime, options)
```

### Parameters

- `otherDateTime`
  - : Another date and time as either a
    {{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainDateTime.from()','Temporal.PlainDateTime.from()')}}.
- `options` {{optional_inline}}

  - : An object with properties defining how the rounding operation should be
    carried out. The allowed properties are:

    - `largestUnit`

      - : A string defining the largest unit of time allowed in the returned
        object. Valid values are:

        - `'auto'` (default)
        - `'years'`
        - `'months'`
        - `'weeks'`
        - `'days'`
        - `'hours'`
        - `'minutes'`
        - `'seconds'`
        - `'milliseconds'`
        - `'microseconds'`
        - `'nanoseconds'` The `largestUnit` option controls how the resulting
          duration is expressed. A value of `'auto'` means `'days'` unless the
          value of `smallestUnit` is `'years'`, `'months'`, or `'weeks'`, in
          which case `'auto'` means to match the value of `smallestUnit`.

        The returned
        {{jsxref('Temporal/Duration','Temporal.Duration')}}
        object will not have any nonzero fields that are larger than the unit in
        `largestUnit`. A difference of one year and two months will become 14
        months when `largestUnit` is `'months'`, for example. However, a
        difference of one month will still be one month even if `largestUnit` is
        `'years'`.

        > **Warning:** Take care when using `'milliseconds'`, `'microseconds'`,
        > or `'nanoseconds'` as the largest unit. For some durations, the
        > resulting value may overflow
        > {{jsxref('Number/MAX_SAFE_INTEGER','Number.MAX_SAFE_INTEGER')}}
        > and lose precision in its least significant digit(s). Nanoseconds
        > values will overflow and lose precision after about 104 days.
        > Microseconds can fit about 285 years without losing precision, and
        > milliseconds can handle about 285,000 years without losing precision.

    - `smallestUnit`
      - : A string defining the smallest unit of time allowed in the returned
        object. Any fraction of time smaller than this will be rounded to the
        smallest unit. Valid values are the same as for `largestUnit`, except
        the default value is `'nanoseconds'`, which means no rounding will
        occur.
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
object representing the difference between the two dates and times.

## Examples

```js
dt1 = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt2 = Temporal.PlainDateTime.from('2019-01-31T15:30');
dt2.since(dt1); // => P8456DT12H5M29.9999965S
```
