---
title: Temporal.PlainTime.prototype.nanosecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/nanosecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`nanosecond`** read-only property returns a number that identifies the
nanosecond component of the `PlainTime` object.

## Syntax

```js
time.nanosecond
```

### Value

An integer representing the nanosecond component.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.nanosecond; // => 205
```
