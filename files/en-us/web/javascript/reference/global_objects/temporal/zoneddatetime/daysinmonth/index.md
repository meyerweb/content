---
title: Temporal.ZonedDateTime.prototype.daysInMonth
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/daysInMonth
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`daysInMonth`** read-only property gives the number of days in the month
containing the date.

## Syntax

```js
datetime.daysInMonth
```

### Value

An integer representing the number of days in the month. In the ISO 8601
calendar, this is `28`, `29`, `30`, or `31`, depending on the month and whether
the year is a leap year.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23');
datetime.daysInMonth; // => 28

datetime = Temporal.ZonedDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.daysInMonth; // => 30
```
