---
title: Temporal.Instant.prototype.epochNanoseconds
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/epochNanoseconds
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

<p class="summary"><span class="seoSummary">The <strong><code>epochNanoseconds</code></strong> read-only property returns the number of nanoseconds between the Unix epoch and the <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object.</span></p>

## Syntax

```js
instant.epochNanoseconds
```

### Value

An integer representation of the number of nanoseconds (10<sup>−9</sup> seconds)
between the Unix epoch (midnight UTC on January 1, 1970) and `instant`. The
number of nanoseconds is truncated towards zero.

## Examples

```js
instant = Temporal.Instant.from('2019-03-30T01:45+01:00');
instant.epochNanoseconds; // => 1554000300000000000
```
