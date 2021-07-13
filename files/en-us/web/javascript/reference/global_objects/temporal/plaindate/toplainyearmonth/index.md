---
title: Temporal.PlainDate.prototype.toPlainYearMonth()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/toPlainYearMonth
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainYearMonth()</code></strong> method converts a <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object into a <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> object that is the same as the year and month components of the <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object.</span></p>

## Syntax

```js
toPlainYearMonth()
```

### Parameters

None.

### Return value

A
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
object that replicates the year and month components of the original
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`.

## Examples

```js
date = Temporal.PlainDate.from('2006-08-24');
date.toPlainYearMonth(); // => 2006-08
```
