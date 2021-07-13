---
title: Temporal.PlainTime.prototype.with()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/with
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>with()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}</code> object which is a modification of the original object using new property values.</span></p>

## Syntax

```js
with(newValues)
with(newValues, options)
```

### Parameters

- `newValues`
  - : An object containing some or all of the properties accepted by
    `{{jsxref('Temporal/PlainTime/from','Temporal.PlainTime.from()')}}`.
    <div class="note"><strong>Note:</strong> <code>calendar</code> and <code>timeZone</code> properties are not allowed on <var>newValues</var>. See the methods <code>{{jsxref('Temporal/PlainTime/toPlainDateTime','toPlainDateTime()')}}</code> and <code>{{jsxref('Temporal/PlainTime/toZonedDateTime','toZonedDateTime()')}}</code>.<p></p></div>
- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainTime` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _newValues_ are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'`
          - : Out-of-range values will cause the function to throw a
            `RangeError`.

### Return value

A new `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
object.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
// Get the beginning of the hour
time.with({
  minute: 0,
  second: 0,
  millisecond: 0,
  microsecond: 0,
  nanosecond: 0
}); // => 19:00:00
```
