---
title: Temporal.PlainDate.prototype.until()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/until
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

The **`until()`** method computes the elapsed time from the date represented by
`plainDate` until another date, optionally rounds it, and returns it as a
{{jsxref('Temporal/Duration','Temporal.Duration')}} object.If
the second date is earlier than the first, then the resulting duration will be
negative. This method is similar to
{{jsxref('Temporal.PlainDate/since','Temporal.PlainDate.since()')}},
but reversed.

> **Warning:** Computing the difference between dates in different calendar
> systems is not supported. If you need to do this, choose the calendar in which
> the computation takes place by converting one of the dates using the method
> {{jsxref('Temporal.PlainDate/withCalendar','withCalendar()')}}.

## Syntax

```js
until(otherDate)
until(otherDate, options)
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
earlier.until(later);                           // => P4543D
earlier.until(later, { largestUnit: 'years' }); // => P12Y5M7D
later.until(earlier, { largestUnit: 'years' }); // => -P12Y5M7D

// If you really need to calculate the difference between two Dates in
// hours, you can eliminate the ambiguity by explicitly choosing the
// point in time from which you want to reckon the difference. For
// example, using noon:
noon = Temporal.PlainTime.from('12:00');
earlier.toPlainDateTime(noon).until(later.toPlainDateTime(noon), { largestUnit: 'hours' });
  // => PT109032H
  
```
