---
title: Temporal.PlainDateTime.prototype.second
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/second
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`second`** read-only property returns a number that identifies the second
component of the `PlainDateTime` object.

## Syntax

```js
datetime.second
```

### Value

An integer representing the second component.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.second;      // => 30
```
