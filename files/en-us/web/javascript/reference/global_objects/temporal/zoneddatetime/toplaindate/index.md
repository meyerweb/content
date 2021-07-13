---
title: Temporal.ZonedDateTime.prototype.toPlainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toPlainDate
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainDate()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object that corresponds to the date (not time) components of the <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object.</span></p>

## Syntax

```js
toPlainDate()
```

### Parameters

None.

### Return value

A new `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Johannesburg]');
zdt.toPlainDate(); // => 1995-12-07
```
