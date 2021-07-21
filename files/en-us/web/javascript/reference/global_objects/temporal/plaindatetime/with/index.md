---
title: Temporal.PlainDateTime.prototype.with()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/with
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`with()`** method returns a new
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object which is a modification of the original object using new property values.

## Syntax

```js
with(newValues)
with(newValues, options)
```

### Parameters

- `newValues`
  - : An object containing some or all of the properties accepted by
    {{jsxref('Temporal/PlainDateTime/from','Temporal.PlainDateTime.from()')}}.
    > **Note:** `calendar` and `timeZone` properties are not allowed on
    > _newValues_. See the methods
    > {{jsxref('Temporal/PlainDateTime/withCalendar','withCalendar()')}}
    > and
    > {{jsxref('Temporal/PlainDateTime/toZonedDateTime','toZonedDateTime()')}}.
- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainDateTime` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _newValues_ are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'`
          - : Out-of-range values will cause the function to throw a
            `RangeError`.

### Return value

A new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object. If the result is earlier or later than the range of dates
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
can represent (approximately half a million years centered on the Unix epoch),
this method will throw a `RangeError` regardless of the value of `overflow`.

## Examples

```js
dateTime = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dateTime.with({ year: 2015, second: 31 }); // => 2015-12-07T03:24:31.0000035
```
