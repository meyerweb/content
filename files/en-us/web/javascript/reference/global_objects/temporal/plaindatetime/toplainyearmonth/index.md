---
title: Temporal.PlainDateTime.prototype.toPlainYearMonth()
slug: >-
  Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/toPlainYearMonth
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainYearMonth()</code></strong> method returns a <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> object that corresponds to the year and month components of the <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code> object.</span></p>

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
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`.

## Examples

```js
date = Temporal.PlainDateTime.from('2006-08-24');
date.toPlainYearMonth(); // => 2006-08
```
