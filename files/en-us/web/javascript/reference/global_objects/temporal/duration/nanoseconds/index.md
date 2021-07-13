---
title: Temporal.Duration.nanoseconds
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/nanoseconds
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>nanoseconds</code></strong> read-only property returns the value of the nanoseconds component of the <code>{{jsxref('Temporal.Duration','Temporal.Duration')}}</code> object.</span></p>

## Syntax

```js
duration.nanoseconds
```

### Value

An integer.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.nanoseconds; // => 321
```
