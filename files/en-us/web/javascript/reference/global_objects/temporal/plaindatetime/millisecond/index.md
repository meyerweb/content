---
title: Temporal.PlainDateTime.prototype.millisecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/millisecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`millisecond`** read-only property returns a number that identifies the
millisecond component of the `PlainDateTime` object.

## Syntax

```js
datetime.millisecond
```

### Value

An integer representing the millisecond component.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.millisecond; // => 0
```
