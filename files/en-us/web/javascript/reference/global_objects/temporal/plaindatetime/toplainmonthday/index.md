---
title: Temporal.PlainDateTime.prototype.toPlainMonthDay()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/toPlainMonthDay
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainMonthDay()</code></strong> method returns a <code>{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}</code> object that corresponds to the month and day components of the <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code> object.</span></p>

## Syntax

```js
toPlainMonthDay()
```

### Parameters

None.

### Return value

A
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`
object that replicates the month and day components of the original
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`.

## Examples

```js
date = Temporal.PlainDateTime.from('2006-08-24');
date.toPlainMonthDay(); // => 08-24
```
