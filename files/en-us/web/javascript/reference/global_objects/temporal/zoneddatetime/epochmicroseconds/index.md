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

<p class="summary"><span class="seoSummary">The <strong><code>epochMicroseconds</code></strong> read-only property returns the number of full microseconds between the <code>{{jsxref('Temporal.zonedDateTime','Temporal.zonedDateTime')}}</code> object and 00:00 UTC on 1970-01-01, otherwise known as the UNIX Epoch. Any fractional remainders are truncated towards zero.</span></p>

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
