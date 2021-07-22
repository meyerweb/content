---
title: Temporal.PlainYearMonth.prototype.calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/calendar
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`calendar`** read-only property returns an object containing the calendar
in which the {{jsxref('Temporal/PlainYearMonth/year','year')}}
and {{jsxref('Temporal/PlainYearMonth/month','month')}}
properties are interpreted.

## Syntax

```js
yearMonth.calendar
```

### Value

A {{jsxref('Temporal/Calendar','Temporal.Calendar')}} object
representing the calendar system used to determine the month and year.

## Examples

```js
ym = Temporal.PlainYearMonth.from('08-24');
ym.calendar; // returns a Temporal.Calendar object of the ISO 8601 calendar

ym = Temporal.PlainYearMonth.from('2019-02-20[u-ca=hebrew]');
ym.calendar; // returns a Temporal.Calendar object of the Hebrew calendar
```
