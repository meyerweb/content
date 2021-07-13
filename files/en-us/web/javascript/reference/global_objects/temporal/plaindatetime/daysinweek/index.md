---
title: Temporal.PlainDateTime.prototype.daysInWeek
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/daysInWeek
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>daysInWeek</code></strong> read-only property gives the number of days in the week containing the date.</span></p>

## Syntax

```js
datetime.daysInWeek
```

### Value

An integer representing the number of days in the week in which the date occurs.
In the ISO 8601 calendar, this is always `7`, but in other calendar systems the
value may vary from week to week.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2021-04-27');
datetime.daysInWeek; // => 7
```
