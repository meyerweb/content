---
title: Temporal.ZonedDateTime.prototype.epochSeconds
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/epochSeconds
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`epochSeconds`** read-only property returns the number of full seconds
between the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object and 00:00 UTC on 1970-01-01, otherwise known as the UNIX Epoch. Any
fractional remainders are truncated towards zero.

## Syntax

```js
datetime.epochSeconds
```

### Value

A number which is always an integer.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('2020-02-01T12:30+09:00[Asia/Tokyo]');
epochSecs = zdt.epochSeconds;
  // => 1580527800
```
