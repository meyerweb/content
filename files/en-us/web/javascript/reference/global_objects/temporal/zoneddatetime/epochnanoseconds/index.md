---
title: Temporal.ZonedDateTime.prototype.epochNanoseconds
slug: >-
  Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/epochNanoseconds
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`epochNanoseconds`** read-only property returns the number of full
nanoseconds between the
{{jsxref('Temporal.zonedDateTime','Temporal.zonedDateTime')}}
object and 00:00 UTC on 1970-01-01, otherwise known as the UNIX Epoch.

## Syntax

```js
datetime.epochNanoseconds
```

### Value

A {{jsxref('BigInt')}}.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('2020-02-01T12:30+09:00[Asia/Tokyo]');
epochNanos = zdt.epochNanoseconds;
  // => 1580527800000000000n
```
