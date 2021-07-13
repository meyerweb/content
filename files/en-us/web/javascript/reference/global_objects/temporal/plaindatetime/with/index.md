---
title: Temporal.PlainDateTime.prototype.with()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/with
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>with()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code> object which is a modification of the original object using new property values.</span></p>

## Syntax

```js
with(newValues)
with(newValues, options)
```

### Parameters

- `newValues`
  - : An object containing some or all of the properties accepted by
    `{{jsxref('Temporal/PlainDateTime/from','Temporal.PlainDateTime.from()')}}`.
    <div class="note"><strong>Note:</strong> <code>calendar</code> and <code>timeZone</code> properties are not allowed on <var>newValues</var>. See the methods <code>{{jsxref('Temporal/PlainDateTime/withCalendar','withCalendar()')}}</code> and <code>{{jsxref('Temporal/PlainDateTime/toZonedDateTime','toZonedDateTime()')}}</code>.<p></p></div>
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
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
object. If the result is earlier or later than the range of dates
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`
can represent (approximately half a million years centered on the Unix epoch),
this method will throw a `RangeError` regardless of the value of `overflow`.

## Examples

```js
dateTime = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dateTime.with({ year: 2015, second: 31 }); // => 2015-12-07T03:24:31.0000035
```
