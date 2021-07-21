---
title: Temporal.ZonedDateTime.prototype.toPlainMonthDay()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toPlainMonthDay
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
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
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
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Johannesburg]');
zdt.toPlainMonthDay(); // => 12-07
```
