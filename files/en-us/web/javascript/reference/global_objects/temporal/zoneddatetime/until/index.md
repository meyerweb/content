---
title: Temporal.ZonedDateTime.prototype.until()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/until
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

The **`until()`** method computes the elapsed time from the date and time
represented by `ZonedDateTime` until another date and time, optionally rounds
it, and returns it as a
{{jsxref('Temporal/Duration','Temporal.Duration')}} object.If
the second date and time is earlier than the first, then the resulting duration
will be negative. This method is similar to
{{jsxref('Temporal.ZonedDateTime/since','Temporal.ZonedDateTime.since()')}},
but reversed.

The duration returned is a "hybrid" duration. This means that the duration's
date portion represents full calendar days like
{{jsxref('Temporal.PlainDateTime/until','Temporal.PlainDateTime.until()')}}
would return, while its time portion represents real-world elapsed time like
{{jsxref('Temporal.Instant/until','Temporal.Instant.until()')}}
would return. This "hybrid duration" approach automatically adjusts for DST and
matches widely-adopted industry standards like RFC 5545 (iCalendar). It also
matches the behavior of popular JavaScript libraries like moment.js and
date-fns.

Examples:

- The difference between 2:30AM on the day before DST starts and 3:30AM on the
  day DST starts results in `P1DT1H`, even though it's only 24 hours of
  real-world elapsed time
- The difference between 1:45AM on the day before DST starts and the "second"
  1:15AM on the day DST ends results in `PT24H30M` because it hasn't been a full
  calendar day even though it's been 24.5 real-world hours.

> **Warning:** Computing the difference between dates and times in different
> calendar systems is not supported. If you need to do this, choose the calendar
> in which the computation takes place by converting one of the dates and times
> using the method
> {{jsxref('Temporal.ZonedDateTime/withCalendar','.withCalendar()')}}.

## Syntax

```js
until(otherZonedDateTime)
until(otherZonedDateTime, options)
```

### Parameters

- `otherZonedDateTime`
  - : Another month as either a
    {{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/ZonedDateTime.from()','Temporal.ZonedDateTime.from()')}}.
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
          duration is expressed. A value of `'auto'` means `'hours'` unless the
          value of `smallestUnit` is `'years'`, `'months'`, `'weeks'`, or
          `'days'`, in which case `'auto'` means to match the value of
          `smallestUnit`.

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
        object. Valid values are the same as for `largestUnit`, except the
        default value is `'nanoseconds'`, which means no rounding will occur.
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
zdt1 = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500+05:30[Asia/Kolkata]');
zdt2 = Temporal.ZonedDateTime.from('2019-01-31T15:30+05:30[Asia/Kolkata]');
zdt1.until(zdt2);
  // => PT202956H5M29.9999965S
zdt1.until(zdt2, { largestUnit: 'years' });
  // => P23Y1M24DT12H5M29.9999965S
zdt2.until(zdt1, { largestUnit: 'years' });
  // => -P23Y1M24DT12H5M29.9999965S
zdt1.until(zdt2, { largestUnit: 'nanoseconds' });
  // => PT730641929.999996544S
  // (precision lost)

// Rounding, for example if you don't care about sub-seconds
zdt1.until(zdt2, { smallestUnit: 'seconds' });
  // => PT202956H5M29S

// Months and years can be different lengths
[jan1, feb1, mar1] = [1, 2, 3].map((month) =>
  Temporal.ZonedDateTime.from({ year: 2020, month, day: 1, timeZone: 'Asia/Seoul' })
);
jan1.until(feb1, { largestUnit: 'days' }); // => P31D
jan1.until(feb1, { largestUnit: 'months' }); // => P1M
feb1.until(mar1, { largestUnit: 'days' }); // => P29D
feb1.until(mar1, { largestUnit: 'months' }); // => P1M
jan1.until(mar1, { largestUnit: 'days' }); // => P60D
```
