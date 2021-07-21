---
title: Temporal.PlainYearMonth.prototype.eraYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/eraYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`eraYear`** read-only property returns a number identifying the year of
the era in which the date occurs, in calendar systems that use eras.

## Syntax

```js
date.eraYear
```

### Value

An integer representing the year of the era containing the year, or `undefined`
in calendar systems that do not use eras.

> **Note:** Unlike
> {{jsxref('Temporal.PlainYearMonth/year','year')}}, `eraYear`
> may decrease as time proceeds because some eras (like the BCE era in the
> Gregorian calendar) count years backwards.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-06');
ym.eraYear; // => undefined

ym = Temporal.PlainYearMonth.from('2019-02-23[u-ca=gregory]');
ym.eraYear; // => 2019
```
