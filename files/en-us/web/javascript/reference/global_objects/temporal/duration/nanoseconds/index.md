---
title: Temporal.Duration.nanoseconds
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/nanoseconds
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`nanoseconds`** read-only property returns the value of the nanoseconds
component of the
{{jsxref('Temporal.Duration','Temporal.Duration')}} object.

## Syntax

```js
duration.nanoseconds
```

### Value

An integer.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.nanoseconds; // => 321
```
