---
title: Temporal.PlainYearMonth.prototype.with()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/with
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

<p class="summary"><span class="seoSummary">The <strong><code>with()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> object which is a modification of the original object using new property values.</span> This can be used to find the last month of the year in which a date occurs, or to shift a date from one month to another.</p>

## Syntax

```js
with(newValues)
with(newValues, options)
```

### Parameters

- `newValues`
  - : An object containing some or all of the properties accepted by
    `{{jsxref('Temporal/PlainYearMonth/from','Temporal.PlainYearMonth.from()')}}`.
    <div class="note"><strong>Note:</strong> <code>calendar</code> and <code>timeZone</code> properties are not allowed on <var>newValues</var>. It is not possible to convert a <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> to another calendar system without knowing the day of the month.<p></p></div>
- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainYearMonth` object. These are:
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
`{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
object.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2021-04');
// Get December of that year
ym.with({ month: 12 }); // => 2021-12
```

```js
md = Temporal.PlainYearMonth.from('2021-04');
```
