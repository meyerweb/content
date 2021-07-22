---
title: Temporal.Duration.prototype.round()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/round
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
{{jsxref('Temporal/Duration','Temporal.Duration')}} object by
rounding a {{jsxref('Temporal/Duration','Temporal.Duration')}}
object.

## Syntax

```js
round(options)
```

### Parameters

- `options`

  - : An object with properties defining how the rounding operation should be
    carried out. The allowed properties are:

    - `largestUnit`

      - : A string defining the largest unit of time to allow in the rounded
        result. Valid values are:

        - `'auto'` **(default)**
        - `'years'`
        - `'months'`
        - `'weeks'`
        - `'days'`
        - `'hours'`
        - `'minutes'`
        - `'seconds'`
        - `'milliseconds'`
        - `'microseconds'`
        - `'nanoseconds'` The `largestUnit` value determines the largest unit
          allowed in the result. It causes units larger than `largestUnit` to be
          converted into smaller units, and units smaller than `largestUnit` to
          be converted into larger units as much as possible. For example, with
          `largestUnit: 'minutes'`, a duration of 1 hour and 125 seconds will be
          converted into a duration of 62 minutes and 5 seconds.

        A `largestUnit` value of `'auto'` means that `largestUnit` will use
        largest nonzero unit in the duration that is larger than `smallestUnit`.
        For example, in a duration of 3 days and 12 hours, `largestUnit: 'auto'`
        would mean the same as `largestUnit: 'days'`.

        > **Warning:** At least one of `largestUnit` and `smallestUnit` is
        > **required**.

    - `smallestUnit`
      - : A string defining the unit of time to which to round. Valid values are
        the same as for `largestUnit`, with two exceptions: there is no `'auto'`
        value, and the default value is `'nanoseconds'` (which means no rounding
        is performed).
        > **Warning:** At least one of `largestUnit` and `smallestUnit` is
        > **required**.
    - `relativeTo`
      - : The starting point to use when converting between years, months,
        weeks, and days, expressed as a
        {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
        object, or else a value convertible to one.
        > **Warning:** If either `largestUnit` or `smallestUnit` is `'years'`,
        > `'months'`, or `'weeks'`, or if the base duration has nonzero value
        > for any of years, months, or weeks, then the `relativeTo` option is
        > **required**.
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
          - : Always round up, toward positive infinity. For negative durations,
            this option will **decrease** the absolute value of the duration,
            which may be unexpected; e.g., `-3.7` will be rounded to `-3`. To
            round away from zero, use `'ceil'` for positive durations and
            `'floor'` for negative durations.
        - `'floor'`
          - : Always round down, toward negative infinity. For negative
            durations, this option will **increase** the absolute value of the
            result, which may be unexpected; e.g., `-3.2` will be rounded to
            `-4`. For this reason, `'trunc'` is recommended for most "round
            down" use cases.
        - `'trunc'`
          - : Always round toward zero. This will decrease the absolute value of
            all durations, positive or negative.
        - `'halfExpand'` (default)
          - : Round to the nearest of the values allowed by `roundingIncrement`
            and `smallestUnit`. When there is a tie, round away from zero like
            `'ceil'` for positive durations and like `'floor'` for negative
            durations.

### Return value

A new {{jsxref('Temporal/Duration','Temporal.Duration')}}
object representing the rounded-off duration.

## Examples

```js
// Balance a duration as far as possible without knowing a starting point
d = Temporal.Duration.from({ minutes: 130 });
d.round({ largestUnit: 'days' }); // => PT2H10M

// Round to the nearest unit
d = Temporal.Duration.from({ minutes: 10, seconds: 52 });
d.round({ smallestUnit: 'minutes' }); // => PT11M
d.round({ smallestUnit: 'minutes', roundingMode: 'trunc' }); // => PT10M

// How many seconds in a multi-unit duration?
d = Temporal.Duration.from('PT2H34M18S');
d.round({ largestUnit: 'seconds' }).seconds; // => 9258

// Normalize, with and without taking DST into account
d = Temporal.Duration.from({ hours: 2756 });
d.round({
   relativeTo: '2020-01-01T00:00+01:00[Europe/Rome]',
   largestUnit: 'years'
}); // => P114DT21H
    // (one hour longer because DST skipped an hour)
d.round({
  relativeTo: '2020-01-01',
  largestUnit: 'years'
}); // => P114DT20H
    // (one hour shorter if ignoring DST)

// Normalize days into months or years
d = Temporal.Duration.from({ days: 190 });
refDate = Temporal.PlainDate.from('2020-01-01');
d.round({ relativeTo: refDate, largestUnit: 'years' }); // => P6M8D

// Same, but in a different calendar system
d.round({
  relativeTo: refDate.withCalendar('hebrew'),
  largestUnit: 'years'
}); // => P6M13D

// Round a duration up to the next 5-minute billing period
d = Temporal.Duration.from({ minutes: 6 });
d.round({
  smallestUnit: 'minutes',
  roundingIncrement: 5,
  roundingMode: 'ceil'
}); // => PT10M

// How many full 3-month quarters of this year, are in this duration?
d = Temporal.Duration.from({ months: 10, days: 15 });
d = d.round({
  smallestUnit: 'months',
  roundingIncrement: 3,
  roundingMode: 'trunc',
  relativeTo: Temporal.now.plainDateISO()
});
quarters = d.months / 3;
quarters; // => 3
```
