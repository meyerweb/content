---
title: Temporal.ZonedDateTime.prototype.nanosecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/nanosecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`nanosecond`** read-only property returns a number that identifies the
nanosecond component of the `Temporal.ZonedDateTime` object.The number is an
integer in the range 0 through 999, inclusive.

## Syntax

```js
datetime.nanosecond
```

### Value

An integer representing the nanosecond component.

## Examples

```js
dt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500');
dt.nanosecond;  // => 500
```
