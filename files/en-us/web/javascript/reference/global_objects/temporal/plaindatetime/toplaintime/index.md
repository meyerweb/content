---
title: Temporal.PlainDateTime.prototype.toPlainTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/toPlainTime
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainTime()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}</code> object that corresponds to the time of the <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code> object.</span></p>

## Syntax

```js
toPlainTime()
```

### Parameters

None.

### Return value

A new `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
object.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.toPlainTime(); // => 03:24:30.0000035
```
