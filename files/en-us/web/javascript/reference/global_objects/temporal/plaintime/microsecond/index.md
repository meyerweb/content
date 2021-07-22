---
title: Temporal.PlainTime.prototype.microsecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/microsecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`microsecond`** read-only property returns a number that identifies the
microsecond component of the `PlainTime` object.

## Syntax

```js
time.microsecond
```

### Value

An integer representing the microsecond component.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.microsecond; // => 346
```
