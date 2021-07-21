---
title: Temporal.Duration.compare()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/compare
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

The **`compare()`** static method compares two durations and returns an integer
indicating whether the first is shorter, longer, or the same as the
second.Negative durations are treated as the same as negative numbers for
comparison purposes: they are "less" (shorter) than zero.

## Syntax

```js
compare(durationOne, durationTwo);
compare(durationOne, durationTwo, options);
```

### Parameters

- `durationOne`

  `durationTwo`

  - : Either a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object,
    or a value that can be converted to one as if passed to
    {{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}.

- `options` {{optional_inline}}(see note)

  - : An object with properties representing options for the operation. The
    following option is recognized:

    - `relativeTo` \* : The starting point to use when converting between years,
      months, weeks, and days, expressed as a
      {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
      or
      {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
      objects, or else a value convertible to one of those.

              If `relativeTo` is a {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}} object, time zone offset changes will be taken into account when comparing days with hours. If `relativeTo` is a {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}} object, then days are always considered equal to 24 hours.

              If `relativeTo` is neither a {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}} nor a {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}, it will be converted to one of the two as if it were first attempted with {{jsxref('Temporal.ZonedDateTime/from','Temporal.ZonedDateTime.from()')}} and then, if that fails, with {{jsxref('Temporal.PlainDateTime/from','Temporal.PlainDateTime.from()')}}.

      > **Note:** If any of the `years`, `months`, or `weeks` properties of
      > either of the durations are nonzero, then the `relativeTo` option (and
      > thus the _options_ object) is **required**. This is because comparing
      > durations with years, months, or weeks requires a point on the calendar
      > to figure out how long they are.

### Return value

An integer indicating whether `durationOne` is longer than, shorter than, or
equal to `durationTwo`. The possible returned values are:

- `−1` if `durationOne` is shorter than `durationTwo`;
- `0` if `durationOne` and `durationTwo` are the same length;
- `1` if `durationOne` is longer `durationTwo`.

## Examples

```js
one = Temporal.Duration.from({ hours: 79, minutes: 10 });
two = Temporal.Duration.from({ days: 3, hours: 7, seconds: 630 });
three = Temporal.Duration.from({ days: 3, hours: 6, minutes: 50 });
sorted = [one, two, three].sort(Temporal.Duration.compare);
sorted.join(' | ');
// => "P3DT6H50M | PT79H10M | P3DT7H630S"

// Sorting relative to a date, taking DST changes into account:
relativeTo = Temporal.ZonedDateTime.from('2020-11-01T00:00-07:00[America/Los_Angeles]');
sorted = [one, two, three].sort((one, two) => Temporal.Duration.compare(one, two, {relativeTo}));
sorted.join(' | ');
// => "PT79H10M | P3DT6H50M | P3DT7H630S"
```
