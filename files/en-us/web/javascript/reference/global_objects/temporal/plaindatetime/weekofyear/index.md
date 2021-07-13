---
title: Temporal.PlainDateTime.prototype.weekOfYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/weekOfYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>weekOfYear</code></strong> read-only property gives the ISO week number in which the date falls.</span> In the ISO 8601 and Gregorian calendars, this will be a number from <code>1</code> to <code>52</code> or <code>53</code> inclusive. ISO week 1 is the week containing the first Thursday of the year.</p>

## Syntax

```js
datetime.weekOfYear
```

### Value

An integer representing the ISO week number in which the date falls.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2021-04-27');
datetime.weekOfYear; // => 17
```
