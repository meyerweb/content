---
title: Temporal.PlainYearMonth.prototype.daysInMonth
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/daysInMonth
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`daysInMonth`** read-only property gives the number of days in the month.

## Syntax

```js
date.daysInMonth
```

### Value

An integer representing the number of days in the month. In the ISO 8601
calendar, this is `28`, `29`, `30`, or `31`, depending on the month and whether
the year is a leap year.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-07');
ym.daysInMonth; // => 31

ym = Temporal.PlainYearMonth.from('2019-02-23[u-ca=hebrew]');
ym.daysInMonth; // => 30
```
