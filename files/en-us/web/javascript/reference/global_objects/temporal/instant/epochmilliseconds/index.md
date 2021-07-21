---
title: Temporal.Instant.prototype.epochMilliseconds
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/epochMilliseconds
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

T

he **`epochMilliseconds`** read-only property returns the number of milliseconds
between the Unix epoch and the
{{jsxref('Temporal/Instant','Temporal.Instant')}} object.

## Syntax

```js
instant.epochMilliseconds
```

### Value

An integer representation of the number of milliseconds (10<sup>−3</sup>
seconds) between the Unix epoch (midnight UTC on January 1, 1970) and `instant`.
The number of milliseconds is truncated towards zero.

## Examples

```js
instant = Temporal.Instant.from('2019-03-30T01:45+01:00');
instant.epochMilliseconds; // => 1554000300000
```
