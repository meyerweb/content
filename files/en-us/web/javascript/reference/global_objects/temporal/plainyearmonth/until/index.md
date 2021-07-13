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

<p class="summary"><span class="seoSummary">The <strong><code>until()</code></strong> method computes the elapsed time from the month represented by <code>yearMonth</code> until the another month, optionally rounds it, and returns it as a <code>{{jsxref('Temporal/Duration','Temporal.Duration')}}</code> object.</span> If the second month is earlier than the first, then the resulting duration will be negative. This method is similar to <code>{{jsxref('Temporal.PlainYearMonth/since','Temporal.PlainYearMonth.since()')}}</code>, but reversed.</p>

## Syntax

```js
until(otherYearMonth)
until(otherYearMonth, options)
```

### Parameters

- `otherYearMonth`
  - : Another month as either a
    `{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
    object, or a value that can be converted to one as if passed to
    `{{jsxref('Temporal/PlainYearMonth.from()','Temporal.PlainYearMonth.from()')}}`.
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
        `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
        object will not have any nonzero fields that are larger than the unit in
        `largestUnit`. A difference of one year and two months will become 14
        months when `largestUnit` is `'months'`, for example. However, a
        difference of one month will still be one month even if `largestUnit` is
        `'years'`.
        <div class="note"><p>Unlike other Temporal types, weeks and lower are not allowed for either <code>largestUnit</code> or <code>smallestUnit</code>, because the data model of <code>Temporal.PlainYearMonth</code> doesn't have that accuracy.
        If you need to calculate the difference between two <code>PlainYearMonth</code> objects in days, convert them to <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> objects and use <code>{{jsxref('Temporal.PlainDate/until','Temporal.PlainDate.until()')}}</code> instead.</p></div>

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
            `{{jsxref('Temporal/Duration.round()','Temporal.Duration.round()')}}`,
            where they do **not** behave identically.

        - `'halfExpand'`
          - : Round to the nearest of the values allowed by `roundingIncrement`
            and `smallestUnit`. If there is a tie, round up, toward the end of
            time.

### Return value

A new `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
object representing the difference between `yearMonth` and _otherYearMonth_.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2006-08');
other = Temporal.PlainYearMonth.from('2019-06');
ym.until(other);                            // => P12Y10M
ym.until(other, { largestUnit: 'months' }); // => P154M
other.until(ym, { largestUnit: 'months' }); // => -P154M
```
