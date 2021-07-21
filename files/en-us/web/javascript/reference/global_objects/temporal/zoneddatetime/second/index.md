---
title: Temporal.ZonedDateTime.prototype.second
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/second
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`second`** read-only property returns a number that identifies the second
component of the `Temporal.ZonedDateTime` object.The number is an integer in the
range 0 through 59, inclusive. If `60` (for a leap second) was provided to
`from()` or `with()`, `59` is stored and will be returned by this property.

## Syntax

```js
datetime.second
```

### Value

An integer representing the second component.

## Examples

```js
dt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500');
dt.second;      // => 30
```
