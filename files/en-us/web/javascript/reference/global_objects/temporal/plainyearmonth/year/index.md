---
title: Temporal.PlainYearMonth.prototype.year
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/year
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`year`** read-only property returns a number that identifies the year in
which the month occurs.

## Syntax

```js
yearMonth.year
```

### Value

A signed integer representing the number of years relative to a
calendar-specific anchor date.

For calendars that use eras, the anchor is usually aligned with the latest era
so that `eraYear === year` for all dates in that era. However, some calendars
(like Japanese) may use a different anchor.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-06');
ym.year; // => 2019

ym = Temporal.PlainYearMonth.from('2019-02-23[u-ca=hebrew]');
ym.year; // => 5779
```
