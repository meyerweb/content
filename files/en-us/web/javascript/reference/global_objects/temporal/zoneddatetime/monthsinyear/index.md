---
title: Temporal.ZonedDateTime.prototype.monthsInYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/monthsInYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>monthsInYear</code></strong> read-only property gives the number of months in the year containing the date.</span> In calendar systems that use leap months, such as Chinese or Hebrew, this can vary.</p>

## Syntax

```js
datetime.monthsInYear
```

### Value

An integer representing the number of months in the year.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23');
datetime.monthsInYear; // => 12

datetime = Temporal.ZonedDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.monthsInYear; // => 13
```
