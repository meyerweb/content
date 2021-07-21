---
title: Temporal.PlainDate.prototype.eraYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/eraYear
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

> **Note:** Unlike {{jsxref('Temporal.PlainDate/year','year')}},
> `eraYear` may decrease as time proceeds because some eras (like the BCE era in
> the Gregorian calendar) count years backwards.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.eraYear; // => undefined

date = Temporal.PlainDate.from('2019-02-23[u-ca=gregory]');
date.eraYear; // => 2019
```
