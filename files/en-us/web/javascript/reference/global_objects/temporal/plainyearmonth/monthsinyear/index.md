---
title: Temporal.PlainYearMonth.prototype.monthsInYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/monthsInYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>monthsInYear</code></strong> read-only property gives the number of months in the year.</span> In calendar systems that use leap months, such as Chinese or Hebrew, this can vary.</p>

## Syntax

```js
date.monthsInYear
```

### Value

An integer representing the number of months in the year.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-07');
ym.monthsInYear; // => 12

ym = Temporal.PlainYearMonth.from('2019-02-23[u-ca=hebrew]');
ym.monthsInYear; // => 13
```
