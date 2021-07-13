---
title: Temporal.PlainYearMonth.prototype.eraYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/eraYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>eraYear</code></strong> read-only property returns a number identifying the year of the era in which the date occurs, in calendar systems that use eras.</span></p>

## Syntax

```js
date.eraYear
```

### Value

An integer representing the year of the era containing the year, or `undefined`
in calendar systems that do not use eras.

<div class="note"><p>Unlike <code>{{jsxref('Temporal.PlainYearMonth/year','year')}}</code>, <code>eraYear</code> may decrease as time proceeds because some eras (like the BCE era in the Gregorian calendar) count years backwards.</p></div>

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-06');
ym.eraYear; // => undefined

ym = Temporal.PlainYearMonth.from('2019-02-23[u-ca=gregory]');
ym.eraYear; // => 2019
```
