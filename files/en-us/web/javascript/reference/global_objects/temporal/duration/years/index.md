---
title: Temporal.Duration.years
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/years
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`years`** read-only property returns the value of the years component of
the {{jsxref('Temporal.Duration','Temporal.Duration')}} object.

## Syntax

```js
duration.years
```

### Value

An integer.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.years; // => 1
```
