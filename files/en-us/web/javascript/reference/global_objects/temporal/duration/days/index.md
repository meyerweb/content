---
title: Temporal.Duration.days
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/days
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`days`** read-only property returns the value of the days component of the
{{jsxref('Temporal.Duration','Temporal.Duration')}} object.

## Syntax

```js
duration.days
```

### Value

An integer.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.days; // => 4
```
