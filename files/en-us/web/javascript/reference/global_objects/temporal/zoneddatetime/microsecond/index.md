---
title: Temporal.ZonedDateTime.prototype.microsecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/microsecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`microsecond`** read-only property returns a number that identifies the
microsecond component of the `Temporal.ZonedDateTime` object.The number is an
integer in the range 0 through 999, inclusive.

## Syntax

```js
datetime.microsecond
```

### Value

An integer representing the microsecond component.

## Examples

```js
dt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500');
dt.microsecond; // => 3
```
