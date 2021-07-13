---
title: Temporal.PlainTime.prototype.millisecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/millisecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>millisecond</code></strong> read-only property returns a number that identifies the millisecond component of the <code>PlainTime</code> object.</span></p>

## Syntax

```js
time.millisecond
```

### Value

An integer representing the millisecond component.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.millisecond; // => 68
```
