---
title: Temporal.Duration.microseconds
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/microseconds
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`microseconds`** read-only property returns the value of the microseconds
component of the
{{jsxref('Temporal.Duration','Temporal.Duration')}} object.

## Syntax

```js
duration.microseconds
```

### Value

An integer.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.microseconds; // => 654
```
