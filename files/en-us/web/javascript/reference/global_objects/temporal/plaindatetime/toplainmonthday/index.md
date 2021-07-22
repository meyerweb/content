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

The **`toPlainMonthDay()`** method returns a
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
object that corresponds to the month and day components of the
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object.

## Syntax

```js
toPlainMonthDay()
```

### Parameters

None.

### Return value

A
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
object that replicates the month and day components of the original
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}.

## Examples

```js
date = Temporal.PlainDateTime.from('2006-08-24');
date.toPlainMonthDay(); // => 08-24
```
