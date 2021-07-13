---
title: Temporal.PlainDateTime.prototype.toPlainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/toPlainDate
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainDate()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object that corresponds to the date of the <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code> object.</span></p>

## Syntax

```js
toPlainDate()
```

### Parameters

None.

### Return value

A new `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
object.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.toPlainDate(); // => 1995-12-07
```
