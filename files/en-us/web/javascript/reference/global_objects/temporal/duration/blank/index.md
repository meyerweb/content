---
title: Temporal.Duration.blank
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/blank
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`sign`** read-only property returns a boolean indicating whether the
{{jsxref('Temporal.Duration','Temporal.Duration')}} object
represents a duration of zero length.If you also need to know whether a
non-zero-length duration is positive or negative, use the
{{jsxref('Temporal.Duration/sign','Temporal.Duration.sign')}}
property instead.

## Syntax

```js
duration.blank
```

### Value

A boolean `true` if the duration is of zero length; otherwise, `false`.

## Examples

```js
d = Temporal.Duration.from('PT0S');
d.blank; // => true
```

```js
d = Temporal.Duration.from({ days: 0, hours: 0, minutes: 0 });
d.blank; // => true
```
