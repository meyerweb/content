---
title: Temporal.PlainDateTime.prototype.millisecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/millisecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>millisecond</code></strong> read-only property returns a number that identifies the millisecond component of the <code>PlainDateTime</code> object.</span></p>

## Syntax

```js
datetime.millisecond
```

### Value

An integer representing the millisecond component.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.millisecond; // => 0
```
