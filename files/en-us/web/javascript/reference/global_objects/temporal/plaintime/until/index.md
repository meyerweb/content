---
title: Temporal.PlainTime.prototype.until()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/until
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

<p class="summary"><span class="seoSummary">The <strong><code>until()</code></strong> method computes the elapsed time from the wall-clock time represented by <code>plainTime</code> until another wall-clock time, optionally rounds it, and returns it as a <code>{{jsxref('Temporal/Duration','Temporal.Duration')}}</code> object.</span> If the second time is earlier than the first, then the resulting duration will be negative. This method is similar to <code>{{jsxref('Temporal.PlainTime/since','Temporal.PlainTime.since()')}}</code>, but reversed.</p>

## Syntax

```js
until(otherTime)
until(otherTime, options)
```

### Parameters

- `otherTime`
  - : Another time as either a
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object, or a value that can be converted to one as if passed to
    `{{jsxref('Temporal/PlainTime.from()','Temporal.PlainTime.from()')}}`.
- `options` {{optional_inline}}

  - : An object with properties defining how the rounding operation should be
    carried out. The allowed properties are:

    - `largestUnit`

      - : A string defining the largest unit of time allowed in the returned
        object. Valid values are:

        - `'auto'`
        - `'hours'`
        - `'minutes'`
        - `'seconds'`
        - `'milliseconds'`
        - `'microseconds'`
        - `'nanoseconds'` (default) The `largestUnit` option controls how the
          resulting duration is expressed. A value of `'auto'` means `'years'`.

        The returned
        `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
        object will not have any nonzero fields that are larger than the unit in
        `largestUnit`. A difference of two hours will become 7200 seconds when
        `largestUnit` is `'seconds'`, for example. However, a difference of 30
        seconds will still be 30 seconds even if `largestUnit` is `'hours'`.
        `'auto'` is treated as `'hours'`

    - `smallestUnit`
      - : A string defining the smallest unit of time allowed in the returned
        object. Valid and default values are the same as for `largestUnit`.
    - `roundingIncrement`
      - : An integer defining the granularity of the rounding of the unit given
        by `smallestUnit`. The default is `1`.
    - `roundingMode`

      - : A string defining how to deal with any remainders. If `roundingMode`
        is not defined, then no rounding will be performed. The valid values
        are:

        - `'ceil'`
          - : Always round up, toward 23:59:59.999999999.
        - `'floor'`

          `'trunc'` (default)

          - : Always round down, toward 0:00. These two rounding modes behave
            identically, but are included for consistency with
            `{{jsxref('Temporal/Duration.round()','Temporal.Duration.round()')}}`,
            where they do **not** behave identically.

        - `'halfExpand'`
          - : Round to the nearest of the values allowed by `roundingIncrement`
            and `smallestUnit`. If there is a tie, round up, toward
            23:59:59.999999999.

### Return value

A new `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
object representing the difference between `plainTime` and _otherTime_.

## Examples

```js
time = Temporal.PlainTime.from('20:13:20.971398099');
time.until(Temporal.PlainTime.from('22:39:09.068346205')); // => PT2H25M48.096948106S
time.until(Temporal.PlainTime.from('19:39:09.068346205')); // => -PT34M11.903051894S

// Rounding, for example if you don't care about sub-seconds
time.until(Temporal.PlainTime.from('22:39:09.068346205'), { smallestUnit: 'seconds' });
  // => PT2H25M48S
```
