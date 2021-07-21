---
title: Temporal.PlainDateTime.prototype.eraYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/eraYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`eraYear`** read-only property returns a number identifying the year of
the era in which the date and time occurs, in calendar systems that use eras.

## Syntax

```js
datetime.eraYear
```

### Value

An integer representing the year of the era containing the year, or `undefined`
in calendar systems that do not use eras.

> **Note:** Unlike
> {{jsxref('Temporal.PlainDateTime/year','year')}}, `eraYear`
> may decrease as time proceeds because some eras (like the BCE era in the
> Gregorian calendar) count years backwards.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2019-02-23');
datetime.eraYear; // => undefined

datetime = Temporal.PlainDateTime.from('2019-02-23[u-ca=gregory]');
datetime.eraYear; // => 2019
```
