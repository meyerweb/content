---
title: Temporal.ZonedDateTime.prototype.toPlainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toPlainDate
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

T

he **`toPlainDate()`** method returns a new
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object
that corresponds to the date (not time) components of the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
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
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Johannesburg]');
zdt.toPlainDate(); // => 1995-12-07
```
