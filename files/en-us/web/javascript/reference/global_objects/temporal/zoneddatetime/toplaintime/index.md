---
title: Temporal.ZonedDateTime.prototype.toPlainTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toPlainTime
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

T

he **`toPlainTime()`** method returns a new
{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}} object
that corresponds to the time (not date) components of the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
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
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Johannesburg]');
zdt.toPlainTime(); // => 03:24:30
```
