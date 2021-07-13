---
title: Temporal.PlainDate.prototype.eraYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/eraYear
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

<div class="note"><p>Unlike <code>{{jsxref('Temporal.PlainDate/year','year')}}</code>, <code>eraYear</code> may decrease as time proceeds because some eras (like the BCE era in the Gregorian calendar) count years backwards.</p></div>

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.eraYear; // => undefined

date = Temporal.PlainDate.from('2019-02-23[u-ca=gregory]');
date.eraYear; // => 2019
```
