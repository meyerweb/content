---
title: Temporal.PlainDateTime.prototype.minute
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/minute
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`minute`** read-only property returns a number that identifies the minute
component of the `PlainDateTime` object.

## Syntax

```js
datetime.minute
```

### Value

An integer representing the minute component.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.minute;      // => 24
```
