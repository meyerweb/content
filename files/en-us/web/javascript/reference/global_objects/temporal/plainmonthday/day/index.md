---
title: Temporal.PlainMonthDay.prototype.day
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/day
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`day`** read-only property returns a number that identifies the day of the
month on which the date occurs.

## Syntax

```js
monthDay.day
```

### Value

A number representing the day of the month.

## Examples

```js
md = Temporal.PlainMonthDay.from('08-24');
md.day; // => 24

md = Temporal.PlainMonthDay.from('2019-02-20[u-ca=hebrew]');
md.day; // => 15
```
