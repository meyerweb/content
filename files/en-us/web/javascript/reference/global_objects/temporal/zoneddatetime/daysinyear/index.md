---
title: Temporal.ZonedDateTime.prototype.daysInYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/daysInYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`daysInYear`** read-only property gives the number of days in the year
containing the date.In the ISO 8601 and Gregorian calendars, this will be `365`
or `366`; in other calendars, such as those which use leap months, the value can
vary widely.

## Syntax

```js
datetime.daysInYear
```

### Value

An integer representing the number of days in the year.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23');
datetime.daysInYear; // => 365

datetime = Temporal.ZonedDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.daysInYear; // => 385
```
