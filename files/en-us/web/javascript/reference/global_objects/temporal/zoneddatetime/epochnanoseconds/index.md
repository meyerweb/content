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

<p class="summary"><span class="seoSummary">The <strong><code>epochNanoseconds</code></strong> read-only property returns the number of full nanoseconds between the <code>{{jsxref('Temporal.zonedDateTime','Temporal.zonedDateTime')}}</code> object and 00:00 UTC on 1970-01-01, otherwise known as the UNIX Epoch.</span></p>

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
