---
title: Temporal.ZonedDateTime.prototype.minute
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/minute
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`minute`** read-only property returns a number that identifies the minute
component of the `Temporal.ZonedDateTime` object.The number is an integer in the
range 0 through 59, inclusive.

## Syntax

```js
datetime.minute
```

### Value

An integer representing the minute component.

## Examples

```js
dt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500');
dt.minute;      // => 24
```
