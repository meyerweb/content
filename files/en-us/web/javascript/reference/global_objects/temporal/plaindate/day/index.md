---
title: Temporal.PlainDate.prototype.day
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/day
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
date.day
```

### Value

A number representing the day of the month.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.day; // => 23

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.day; // => 15
```
