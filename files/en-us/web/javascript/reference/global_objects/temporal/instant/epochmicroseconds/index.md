---
title: Temporal.Instant.prototype.epochMicroseconds
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/epochMicroseconds
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

he **`epochMicroseconds`** read-only property returns the number of microseconds
between the Unix epoch and the
{{jsxref('Temporal/Instant','Temporal.Instant')}} object.

## Syntax

```js
instant.epochMicroseconds
```

### Value

An integer representation of the number of microseconds (10<sup>−6</sup>
seconds) between the Unix epoch (midnight UTC on January 1, 1970) and `instant`.
The number of microseconds is truncated towards zero.

## Examples

```js
instant = Temporal.Instant.from('2019-03-30T01:45+01:00');
instant.epochMicroseconds; // => 1554000300000000
```
