---
title: Temporal.Duration.sign
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/sign
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>sign</code></strong> read-only property returns a value indicating the sign of the <code>{{jsxref('Temporal.Duration','Temporal.Duration')}}</code> object.</span> If you don't need to know whether a non-zero-length duration is positive or negative, use the {{jsxref('Temporal.Duration/blank','Temporal.Duration.blank')}} property instead.</p>

## Syntax

```js
time.sign
```

### Value

One of the three following integers:

- `–1` if the duration is negative
- `0` if the duration is of zero length
- `1` if the duration is positive

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.sign; // => 1
```

```js
d = new Temporal.Duration();  // creates a Duration with all values at zero
d.sign; // => 0
```
