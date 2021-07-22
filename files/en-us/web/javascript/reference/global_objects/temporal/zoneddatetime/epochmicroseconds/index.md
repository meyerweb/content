---
title: Temporal.ZonedDateTime.prototype.epochMicroseconds
slug: >-
  Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/epochMicroseconds
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`epochMicroseconds`** read-only property returns the number of full
microseconds between the
{{jsxref('Temporal.zonedDateTime','Temporal.zonedDateTime')}}
object and 00:00 UTC on 1970-01-01, otherwise known as the UNIX Epoch. Any
fractional remainders are truncated towards zero.

## Syntax

```js
datetime.epochMicroseconds
```

### Value

A {{jsxref('BigInt')}}.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('2020-02-01T12:30+09:00[Asia/Tokyo]');
epochMicros = zdt.epochMicroseconds;
  // => 1580527800000000n
```
