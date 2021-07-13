---
title: Temporal.ZonedDateTime.prototype.dayOfWeek
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/dayOfWeek
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>dayOfWeek</code></strong> read-only property gives the weekday number on which the date falls.</span> In the ISO 8601 calendar, the weekday number is defined as in the ISO 8601 standard: a value between <code>1</code> and <code>7</code>, inclusive, with Monday being <code>1</code>, and Sunday <code>7</code>.</p>

## Syntax

```js
datetime.dayOfWeek
```

### Value

An integer representing the weekday number on which the date falls.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2021-04-27');
datetime.dayOfWeek; // => 2
```
