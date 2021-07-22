---
title: Temporal.Duration.prototype.negated()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/negated
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`sign`** read-only property creates a new
{{jsxref('Temporal/Duration','Temporal.Duration')}} object by
inverting the sign of the original duration.

## Syntax

```js
negated()
```

### Return value

A new {{jsxref('Temporal/Duration','Temporal.Duration')}}
object.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3DT4H5M6.987654321S');
d.sign; // 1
d.negated(); // -P1Y2M3DT4H5M6.987654321S
d.negated().sign; // -1
```
