---
title: Temporal.PlainDateTime.prototype.era
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/era
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>era</code></strong> read-only property returns a string of the era in which the date and time occurs, in calendar systems that use eras.</span></p>

## Syntax

```js
datetime.era
```

### Value

A string rendering of the era's label, or `undefined` in calendar systems that
do not use eras.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2019-02-23');
datetime.era; // => undefined

datetime = Temporal.PlainDateTime.from('2019-02-23[u-ca=gregory]');
datetime.era; // => "ce"
```
