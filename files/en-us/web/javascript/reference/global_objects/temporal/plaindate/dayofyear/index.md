---
title: Temporal.PlainDate.prototype.dayOfYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/dayOfYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>dayOfYear</code></strong> read-only property gives the ordinal day of the year on which the date falls.</span> In the ISO 8601 and Gregorian calendars, this will be a number from <code>1</code> to <code>365</code> or <code>366</code> inclusive. In other calendars, such as those which use leap months, the upper bound can vary widely.</p>

## Syntax

```js
date.dayOfYear
```

### Value

An integer representing the ordinal day of the year on which the date falls.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.dayOfYear; // => 54

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.dayOfYear; // => 243
```
