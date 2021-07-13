---
title: Temporal.ZonedDateTime.prototype.day
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/day
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>day</code></strong> read-only property returns a number that identifies the day of the month on which the date and time occurs.</span></p>

## Syntax

```js
datetime.day
```

### Value

A positive integer representing the day of the month.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23');
datetime.day; // => 23

datetime = Temporal.ZonedDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.day; // => 15
```
