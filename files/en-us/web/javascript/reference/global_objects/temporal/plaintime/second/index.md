---
title: Temporal.PlainTime.prototype.second
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/second
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>second</code></strong> read-only property returns a number that identifies the second component of the <code>PlainTime</code> object.</span></p>

## Syntax

```js
time.second
```

### Value

An integer representing the second component.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.second; // => 9
```
