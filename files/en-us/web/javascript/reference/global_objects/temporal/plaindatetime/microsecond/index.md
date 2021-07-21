---
title: Temporal.PlainDateTime.prototype.microsecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/microsecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`microsecond`** read-only property returns a number that identifies the
microsecond component of the `PlainDateTime` object.

## Syntax

```js
datetime.microsecond
```

### Value

An integer representing the microsecond component.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.microsecond; // => 3
```
