---
title: Temporal.PlainMonthDay.prototype.calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/calendar
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`calendar`** read-only property returns an object containing the calendar
in which the
{{jsxref('Temporal/PlainMonthDay/monthCode','monthCode')}} and
{{jsxref('Temporal/PlainMonthDay/day','day')}} properties are
interpreted.

## Syntax

```js
monthDay.calendar
```

### Value

A {{jsxref('Temporal/Calendar','Temporal.Calendar')}} object
representing the calendar system used to determine the month and day.

## Examples

```js
md = Temporal.PlainMonthDay.from('08-24');
md.calendar; // returns a Temporal.Calendar object of the ISO 8601 calendar

md = Temporal.PlainMonthDay.from('2019-02-20[u-ca=hebrew]');
md.calendar; // returns a Temporal.Calendar object of the Hebrew calendar
```
