---
title: Temporal.PlainDate.prototype.dayOfYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/dayOfYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`dayOfYear`** read-only property gives the ordinal day of the year on
which the date falls.In the ISO 8601 and Gregorian calendars, this will be a
number from `1` to `365` or `366` inclusive. In other calendars, such as those
which use leap months, the upper bound can vary widely.

## Syntax

```js
date.dayOfYear
```

### Value

An integer representing the ordinal day of the year on which the date falls.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.dayOfYear; // => 54

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.dayOfYear; // => 243
```
