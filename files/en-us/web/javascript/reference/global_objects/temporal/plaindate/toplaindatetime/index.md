---
title: Temporal.PlainDate.prototype.toPlainDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/toPlainDateTime
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toPlainDateTime()`** method converts a
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object
into a
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object, by combining a wall-clock time with the date of the
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object.

## Syntax

```js
toPlainDateTime()
toPlainDateTime(time)
```

### Parameters

- `time` {{ optional_inline }}
  - : The wall-clock time to be combined with the date. If _time_ is not a
    {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
    object, then it will be converted to one as if it were passed to
    {{jsxref('Temporal.PlainTime/from','Temporal.PlainTime.from()')}}.
    If _time_ is not defined, its value defaults to midnight (`00:00`).

### Return value

A
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object that represents the combination of date and time.

## Examples

```js
date = Temporal.PlainDate.from('2006-08-24');
time = Temporal.PlainTime.from('15:23:30.003');
date.toPlainDateTime(time); // => 2006-08-24T15:23:30.003
date.toPlainDateTime(); // => 2006-08-24T00:00:00
```
