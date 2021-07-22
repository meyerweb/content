---
title: Temporal.Instant.prototype.until()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/until
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

The **`until()`** method computes the elapsed time from the exact time
represented by `instant` until the exact time represented by `moment`,
optionally rounds it, and returns it as a
{{jsxref('Temporal/Duration','Temporal.Duration')}} object.If
`moment` is earlier than `instant`, then the resulting duration will be
negative. This method is similar to
{{jsxref('Temporal.Instant/since','Temporal.Instant.since()')}},
but reversed.

By default, the largest unit in the result is seconds. Weeks, months, years, and
days are not allowed, unlike the difference methods of the other Temporal types.
This is because months and years can be different lengths depending on which
month is meant, and whether the year is a leap year, which all depends on the
start and end date of the difference. You cannot determine the start and end
date of a difference between
{{jsxref('Temporal/Instant','Temporal.Instant')}}s, because
{{jsxref('Temporal/Instant','Temporal.Instant')}} has no time
zone or calendar. In addition, weeks can be different lengths in different
calendars, and days can be different lengths when the time zone has a daylight
saving transition.

If you do need to calculate the difference between two
{{jsxref('Temporal/Instant','Temporal.Instant')}}s in years,
months, weeks, or days, then you can make an explicit choice on how to eliminate
this ambiguity, choosing your starting point by converting to a
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
or
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}.
For example, you might decide to base the calculation on your user's current
time zone, or on UTC, in the Gregorian calendar.

## Syntax

```js
until(moment)
until(moment, options)
```

### Parameters

- `moment`
  - : An exact time as either a
    {{jsxref('Temporal/Instant','Temporal.Instant')}} object, or
    a value that can be converted to one as if passed to
    {{jsxref('Temporal/Instant.from()','Temporal.Instant.from()')}}.
- `options` {{optional_inline}}

  - : An object with properties defining how the rounding operation should be
    carried out. The allowed properties are:

    - `largestUnit`

      - : A string defining the largest unit of time allowed in the returned
        object. Valid values are:

        - `'auto'` (default)
        - `'hours'`
        - `'minutes'`
        - `'seconds'`
        - `'milliseconds'`
        - `'microseconds'`
        - `'nanoseconds'` The `largestUnit` option controls how the resulting
          duration is expressed. A value of `'auto'` means `'seconds'`, unless
          `smallestUnit` is `'hours'` or `'minutes'`, in which case
          `largestUnit` is equal to `smallestUnit`.

        The returned
        {{jsxref('Temporal/Duration','Temporal.Duration')}}
        object will not have any nonzero fields that are larger than the unit in
        `largestUnit`. A difference of two hours will become 7200 seconds when
        `largestUnit` is `'seconds'`, for example. However, a difference of 30
        seconds will still be 30 seconds even if `largestUnit` is `'hours'`.

        Take care when using milliseconds, microseconds, or nanoseconds as the
        largest unit. For some durations, the resulting value may overflow
        `Number.MAX_SAFE_INTEGER` and lose precision in its least significant
        digit(s). Nanoseconds values will overflow and lose precision after
        about 104 days. Microseconds can fit about 285 years without losing
        precision, and milliseconds can handle about 285,000 years without
        losing precision.

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
object representing the difference between `instant` and `moment`.

## Examples

```js
startOfMoonMission = Temporal.Instant.from('1969-07-16T13:32:00Z');
endOfMoonMission = Temporal.Instant.from('1969-07-24T16:50:35Z');
missionLength = startOfMoonMission.until(endOfMoonMission, { largestUnit: 'days' });
  // => PT195H18M35S
missionLength.toLocaleString();
  // example output: '195 hours 18 minutes 35 seconds'

// Rounding, for example if you don't care about the minutes and seconds
approxMissionLength = startOfMoonMission.until(endOfMoonMission, {
  largestUnit: 'hours',
  smallestUnit: 'hours'
});
  // => P195H

// A billion (10^9) seconds since the epoch in different units
epoch = Temporal.Instant.fromEpochSeconds(0);
billion = Temporal.Instant.fromEpochSeconds(1e9);
epoch.until(billion);
  // =>    PT1000000000S
epoch.until(billion, { largestUnit: 'hours' });
  // =>  PT277777H46M40S
ns = epoch.until(billion, { largestUnit: 'nanoseconds' });
  // =>    PT1000000000S
ns.add({ nanoseconds: 1 });
  // =>    PT1000000000S (lost precision)

// Calculate the difference in years, eliminating the ambiguity by
// explicitly using the corresponding calendar date in UTC:
epoch.toZonedDateTimeISO('UTC').until(
  billion.toZonedDateTimeISO('UTC'),
  { largestUnit: 'years' }
);
  // => P31Y8M8DT1H46M40S
```
