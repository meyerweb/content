---
title: Temporal.PlainDate.prototype.monthsInYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/monthsInYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`monthsInYear`** read-only property gives the number of months in the year
containing the date.In calendar systems that use leap months, such as Chinese or
Hebrew, this can vary.

## Syntax

```js
date.monthsInYear
```

### Value

An integer representing the number of months in the year.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.monthsInYear; // => 12

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.monthsInYear; // => 13
```
