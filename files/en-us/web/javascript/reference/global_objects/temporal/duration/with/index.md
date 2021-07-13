---
title: Temporal.Duration.prototype.with()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/with
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>with()</code></strong> method returns a new <code>{{jsxref('Temporal.Duration','Temporal.Duration')}}</code> object which is a modification of the original object using new property values.</span></p>

## Syntax

```js
with(newValues)
```

### Parameters

- `newValues`

  - : An object containing some or all of the properties accepted by
    `{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}`.

    All non-zero properties of _newValues_ **must** have the same sign, and they
    must additionally have the same sign as the non-zero properties of the
    `Temporal.Duration` object being modified, unless they override **all** of
    the non-zero properties. If a property of _newValues_ is infinity, then this
    function will throw a `RangeError`.

### Return value

A new `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
object.

## Examples

```js
duration = Temporal.Duration.from({ months: 50, days: 50, hours: 50, minutes: 100 });
// Perform a balance operation using additional ISO calendar rules:
let { years, months } = duration;
years += Math.floor(months / 12);
months %= 12;
duration = duration.with({ years, months });
  // => P4Y2M50DT50H100M
```
