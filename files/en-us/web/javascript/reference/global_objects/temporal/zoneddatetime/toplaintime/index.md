---
title: Temporal.ZonedDateTime.prototype.toPlainTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toPlainTime
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainTime()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}</code> object that corresponds to the time (not date) components of the <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object.</span></p>

## Syntax

```js
toPlainTime()
```

### Parameters

None.

### Return value

A new `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Johannesburg]');
zdt.toPlainTime(); // => 03:24:30
```
