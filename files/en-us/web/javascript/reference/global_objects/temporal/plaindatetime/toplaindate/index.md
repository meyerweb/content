---
title: Temporal.PlainDateTime.prototype.toPlainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/toPlainDate
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

T

he **`toPlainDate()`** method returns a new
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object
that corresponds to the date of the
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object.

## Syntax

```js
toPlainDate()
```

### Parameters

None.

### Return value

A new {{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
object.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.toPlainDate(); // => 1995-12-07
```
