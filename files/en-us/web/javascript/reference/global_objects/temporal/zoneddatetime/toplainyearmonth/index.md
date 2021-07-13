---
title: Temporal.ZonedDateTime.prototype.toPlainYearMonth()
slug: >-
  Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toPlainYearMonth
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainYearMonth()</code></strong> method returns a <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> object that corresponds to the year and month components of the <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object.</span></p>

## Syntax

```js
toPlainYearMonth()
```

### Parameters

None.

### Return value

A
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
object that replicates the year and month components of the original
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Johannesburg]');
zdt.toPlainYearMonth(); // => 1995-12
```
