---
title: Temporal.PlainTime.prototype.nanosecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/nanosecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>nanosecond</code></strong> read-only property returns a number that identifies the nanosecond component of the <code>PlainTime</code> object.</span></p>

## Syntax

```js
time.nanosecond
```

### Value

An integer representing the nanosecond component.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.nanosecond; // => 205
```
