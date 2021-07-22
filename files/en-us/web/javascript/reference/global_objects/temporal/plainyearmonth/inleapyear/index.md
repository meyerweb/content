---
title: Temporal.PlainYearMonth.prototype.inLeapYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/inLeapYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`inLeapYear`** read-only property indicates whether the date occurs in a
leap year.

## Syntax

```js
date.inLeapYear
```

### Value

The boolean value `true` if the date occurs in a leap year, or `false` if not.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-07');
ym.inLeapYear; // => false

ym = Temporal.PlainYearMonth.from('2019-02-23[u-ca=hebrew]');
ym.inLeapYear; // => true
```
