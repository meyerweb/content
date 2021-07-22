---
title: Temporal.PlainDate.prototype.subtract()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/subtract
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
{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}} object
by subtracting a duration from a
{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
object.Subtracting a negative duration is equivalent to
{{jsxref('Temporal.PlainDate/add','adding','','nocode')}} the
absolute value of that duration.

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
    the new
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    object. These are:
    - `overflow`
      - : Determines how out-of-range values in the result are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'`
          - : Out-of-range values will cause the function to throw a
            `RangeError`.

### Return value

A new {{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
object representing the calendar date indicated by `PlainDate` minus `duration`.

## Examples

```js
date = Temporal.PlainDate.from('2006-08-24');
date.subtract({ years: 20, months: 4 }); // => 1986-04-24

date = Temporal.PlainDate.from('2019-03-31');
date.subtract({ months: 1 }); // => 2019-02-28
date.subtract({ months: 1 }, { overflow: 'reject' }); // => throws
```
