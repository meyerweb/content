---
title: Temporal.PlainYearMonth.prototype.daysInYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/daysInYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`daysInYear`** read-only property gives the number of days in the year.In
the ISO 8601 and Gregorian calendars, this will be `365` or `366`; in other
calendars, such as those which use leap months, the value can vary widely.

## Syntax

```js
date.daysInYear
```

### Value

An integer representing the number of days in the year.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-07');
ym.daysInYear; // => 365

ym = Temporal.PlainYearMonth.from('2019-02-23[u-ca=hebrew]');
ym.daysInYear; // => 385
```
