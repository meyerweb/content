---
title: Temporal.PlainMonthDay.prototype.with()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/with
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

<p class="summary"><span class="seoSummary">The <strong><code>with()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}</code> object which is a modification of the original object with new property values.</span> This can be used to find the last day of the month in which a date occurs, or to shift a date from one month to another.</p>

## Syntax

```js
with(newValues)
with(newValues, options)
```

### Parameters

- `newValues`
  - : An object containing some or all of the properties accepted by
    `{{jsxref('Temporal/PlainMonthDay/from','Temporal.PlainMonthDay.from()')}}`.
- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainMonthDay` object. These are:
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
`{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}`
object.

## Examples

```js
md = Temporal.PlainMonthDay.from('11-15');
// What's the last day of that month?
md.with({ day: 31 }); // => 11-30
```

```js
md = Temporal.PlainMonthDay.from('01-31');
// Equivalent date in April
md.with({ monthCode: 'M04' }); // => 04-30
```
