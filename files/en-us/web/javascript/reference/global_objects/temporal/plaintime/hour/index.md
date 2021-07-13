---
title: Temporal.PlainTime.prototype.hour
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/hour
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>hour</code></strong> read-only property returns a number that identifies the hour component of the <code>PlainTime</code> object.</span></p>

## Syntax

```js
time.hour
```

### Value

An integer representing the hour component.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.hour; // => 19
```
