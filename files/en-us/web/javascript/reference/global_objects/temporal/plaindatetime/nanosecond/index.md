---
title: Temporal.PlainDateTime.prototype.nanosecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/nanosecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`nanosecond`** read-only property returns a number that identifies the
nanosecond component of the `PlainDateTime` object.

## Syntax

```js
datetime.nanosecond
```

### Value

An integer representing the nanosecond component.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.nanosecond;  // => 500
```
