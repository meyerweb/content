---
title: Temporal.Duration.weeks
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/weeks
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`weeks`** read-only property returns the value of the weeks component of
the {{jsxref('Temporal.Duration','Temporal.Duration')}} object.

## Syntax

```js
duration.weeks
```

### Value

An integer.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.weeks; // => 3
```
