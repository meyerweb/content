---
title: Temporal.ZonedDateTime.prototype.hour
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/hour
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`hour`** read-only property returns a number that identifies the hour
component of the `Temporal.ZonedDateTime` object.The number is an integer in the
range 0 through 23, inclusive.

## Syntax

```js
datetime.hour
```

### Value

An integer representing the hour component.

## Examples

```js
dt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500');
dt.hour; // => 3
```
