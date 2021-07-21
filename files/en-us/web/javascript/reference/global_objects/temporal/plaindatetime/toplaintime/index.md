---
title: Temporal.PlainDateTime.prototype.toPlainTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/toPlainTime
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

T

he **`toPlainTime()`** method returns a new
{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}} object
that corresponds to the time of the
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object.

## Syntax

```js
toPlainTime()
```

### Parameters

None.

### Return value

A new {{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}
object.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.toPlainTime(); // => 03:24:30.0000035
```
