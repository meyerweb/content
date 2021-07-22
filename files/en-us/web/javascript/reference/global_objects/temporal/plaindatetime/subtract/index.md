---
title: Temporal.PlainDateTime.prototype.subtract()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/subtract
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

The **`subtract()`** method creates a new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object by subtracting a duration from a
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object.Subtracting a negative duration is equivalent to
{{jsxref('Temporal.PlainDateTime/add','adding','','nocode')}}
the absolute value of that duration.

## Syntax

```js
subtract(duration)
subtract(duration, options)
```

### Parameters

- `duration`

  - : An object with properties denoting a duration, such as `{ days: 5 }`, or a
    string value such as `P5D`, or a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object.
    If `duration` is not such a string nor a
    {{jsxref('Temporal/Duration','Temporal.Duration')}} object,
    then it will be converted to a string as if it were passed to
    {{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}.

    Some subtractions may be ambiguous, because months have different lengths.
    For example, subtracting `{ month: 1 }` from October 31 would result in
    September 31, which doesn't exist. In such cases, the `overflow` option (see
    below) governs the result.

- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainDate` object. These are:
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
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object representing the calendar date indicated by `oldDateTime` minus
_duration_.

## Examples

```js
datetime = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
datetime.subtract({ years: 20, months: 4, nanoseconds: 500 }); // => 1975-08-07T03:24:30.000003

datetime = Temporal.PlainDateTime.from('2019-03-31T15:30');
datetime.subtract({ months: 1 }); // => 2019-02-28T15:30:00
datetime.subtract({ months: 1 }, { overflow: 'reject' }); // => throws
```
