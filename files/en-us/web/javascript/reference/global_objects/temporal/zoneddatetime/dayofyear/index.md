---
title: Temporal.ZonedDateTime.prototype.dayOfYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/dayOfYear
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
datetime.dayOfYear
```

### Value

An integer representing the ordinal day of the year on which the date falls.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23');
datetime.dayOfYear; // => 54

datetime = Temporal.ZonedDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.dayOfYear; // => 243
```
