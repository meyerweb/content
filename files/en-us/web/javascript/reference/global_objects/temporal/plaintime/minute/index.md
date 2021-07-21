---
title: Temporal.PlainTime.prototype.minute
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/minute
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`minute`** read-only property returns a number that identifies the minute
component of the `PlainTime` object.

## Syntax

```js
time.minute
```

### Value

An integer representing the minute component.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.minute; // => 39
```
