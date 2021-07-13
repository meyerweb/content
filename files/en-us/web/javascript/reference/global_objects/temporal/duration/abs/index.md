---
title: Temporal.Duration.prototype.abs()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/abs
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>sign</code></strong> read-only property creates a new <code>{{jsxref('Temporal/Duration','Temporal.Duration')}}</code> object equal to the absolute value of the original duration; that is, all properties will have the same magnitude as in the original object, but all be positive.</span> If the original object is already zero or positive, then the returned object is a copy of the original.</p>

## Syntax

```js
abs()
```

### Return value

A new `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
object.

## Examples

```js
d = Temporal.Duration.from('-P1Y2M3DT4H5M6.987654321S');
d.sign; // -1
d.abs(); // P1Y2M3DT4H5M6.987654321S
d.abs().sign; // 1
```
