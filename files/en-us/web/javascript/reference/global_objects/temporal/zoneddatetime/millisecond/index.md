---
title: Temporal.ZonedDateTime.prototype.millisecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/millisecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`millisecond`** read-only property returns a number that identifies the
millisecond component of the `Temporal.ZonedDateTime` object.The number is an
integer in the range 0 through 999, inclusive.

## Syntax

```js
datetime.millisecond
```

### Value

An integer representing the millisecond component.

## Examples

```js
dt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500');
dt.millisecond; // => 0
```
