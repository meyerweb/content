---
title: Temporal.PlainDate.prototype.calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/calendar
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`calendar`** read-only property returns an object containing the calendar
in which the {{jsxref('Temporal/PlainDate/year','year')}},
{{jsxref('Temporal/PlainDate/month','month')}}, and
{{jsxref('Temporal/PlainDate/day','day')}} properties are
interpreted.

## Syntax

```js
date.calendar
```

### Value

A {{jsxref('Temporal/Calendar','Temporal.Calendar')}} object
representing the calendar system used to determine the year, month, and day.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.calendar; // returns a Temporal.Calendar object of the ISO 8601 calendar

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.calendar; // returns a Temporal.Calendar object of the Hebrew calendar
```
