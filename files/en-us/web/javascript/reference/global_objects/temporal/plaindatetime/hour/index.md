---
title: Temporal.PlainDateTime.prototype.hour
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/hour
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>hour</code></strong> read-only property returns a number that identifies the hour component of the <code>PlainDateTime</code> object.</span></p>

## Syntax

```js
datetime.hour
```

### Value

An integer representing the hour component.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.hour; // => 3
```
