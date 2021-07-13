---
title: Temporal.PlainDate.prototype.toPlainMonthDay()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/toPlainMonthDay
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainMonthDay()</code></strong> method converts a <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object into a <code>{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}</code> object that is the same as the month and day components of the <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object.</span></p>

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
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`.

## Examples

```js
date = Temporal.PlainDate.from('2006-08-24');
date.toPlainMonthDay(); // => 08-24
```
