---
title: Temporal.Duration.months
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/months
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`months`** read-only property returns the value of the months component of
the {{jsxref('Temporal.Duration','Temporal.Duration')}} object.

## Syntax

```js
duration.months
```

### Value

An integer.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.months; // => 2
```
