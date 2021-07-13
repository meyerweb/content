---
title: Temporal.PlainYearMonth.prototype.era
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/era
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>era</code></strong> read-only property returns a string of the era in which the month occurs, in calendar systems that use eras.</span></p>

## Syntax

```js
yearMonth.era
```

### Value

A string rendering of the era's label, or `undefined` in calendar systems that
do not use eras.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-06');
ym.era; // => undefined

ym = Temporal.PlainYearMonth.from('2019-02-23[u-ca=gregory]');
ym.era; // => "ce"
```
