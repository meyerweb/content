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

The **`toPlainYearMonth()`** method converts a
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object
into a
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
object that is the same as the year and month components of the
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object.

## Syntax

```js
toPlainYearMonth()
```

### Parameters

None.

### Return value

A
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
object that replicates the year and month components of the original
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}.

## Examples

```js
date = Temporal.PlainDate.from('2006-08-24');
date.toPlainYearMonth(); // => 2006-08
```
