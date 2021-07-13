---
title: Temporal.PlainDateTime.prototype.add()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/add
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

<p class="summary"><span class="seoSummary">The <strong><code>add()</code></strong> method creates a new <code>{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}</code> object by adding a duration to a <code>{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}</code> object.</span> Adding a negative duration is equivalent to {{jsxref('Temporal.PlainDateTime/subtract','subtracting')}} the absolute value of that duration.</p>

## Syntax

```js
add(duration)
add(duration, options)
```

### Parameters

- `duration`

  - : An object with properties denoting a duration, such as
    `{ days: 5, hours: 5, minutes: 30 }`, or a string value such as `P5DT5H30M`,
    or a `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object. If `duration` is not such a string nor a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object, then it will be converted to a string as if it were passed to
    `{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}`.

    Some additions may be ambiguous, because months have different lengths. For
    example, adding `{ month: 1 }` to August 31 would result in September 31,
    which doesn't exist. In such cases, the `overflow` option (see below)
    governs the result.

- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainDateTime` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _duration_ are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'`
          - : Out-of-range values will cause the function to throw a
            `RangeError`.

### Return value

A new
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
object representing the calendar date indicated by `oldDateTime` plus
_duration_. If the result is earlier or later than the range of dates that
`Temporal.PlainDateTime` can represent (approximately half a million years
centered on the Unix epoch), this method will throw a `RangeError` regardless of
the value of the `overflow` option.

## Examples

```js
datetime = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
datetime.add({ years: 20, months: 4, nanoseconds: 500 }); // => 2016-04-07T03:24:30.000004

datetime = Temporal.PlainDateTime.from('2019-01-31T15:30');
datetime.add({ months: 1 }); // => 2019-02-28T15:30:00
datetime.add({ months: 1 }, { overflow: 'reject' }); // => throws
```
