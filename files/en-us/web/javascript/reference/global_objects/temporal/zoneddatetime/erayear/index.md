---
title: Temporal.ZonedDateTime.prototype.eraYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/eraYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>eraYear</code></strong> read-only property returns a number identifying the year of the era in which the date and time occurs, in calendar systems that use eras.</span></p>

## Syntax

```js
datetime.eraYear
```

### Value

An integer representing the year of the era containing the year, or `undefined`
in calendar systems that do not use eras.

<div class="note"><p>Unlike <code>{{jsxref('Temporal.ZonedDateTime/year','year')}}</code>, <code>eraYear</code> may decrease as time proceeds because some eras (like the BCE era in the Gregorian calendar) count years backwards.</p></div>

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23');
datetime.eraYear; // => undefined

datetime = Temporal.ZonedDateTime.from('2019-02-23[u-ca=gregory]');
datetime.eraYear; // => 2019
```
