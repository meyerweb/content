---
title: Temporal.PlainDateTime.prototype.dayOfWeek
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/dayOfWeek
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>dayOfWeek</code></strong> read-only property gives the weekday number on which the date falls.</span> In the ISO 8601 calendar, this is always a value from <code>1</code> to <code>7</code> inclusive, where <code>1</code> represents Monday, and <code>7</code> represents Sunday, but the range of values, or alignment of numbers to days, could be different in other calendars.</p>

## Syntax

```js
datetime.dayOfWeek
```

### Value

An integer representing the weekday number on which the date falls.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2021-04-27');
datetime.dayOfWeek; // => 2
```
