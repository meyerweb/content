---
title: Temporal.Duration.days
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/days
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>days</code></strong> read-only property returns the value of the days component of the <code>{{jsxref('Temporal.Duration','Temporal.Duration')}}</code> object.</span></p>

## Syntax

```js
duration.days
```

### Value

An integer.

## Examples

```js
d = Temporal.Duration.from('P1Y2M3W4DT5H6M7.987654321S');
d.days; // => 4
```
