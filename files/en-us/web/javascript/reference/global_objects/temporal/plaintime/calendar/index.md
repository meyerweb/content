---
title: Temporal.PlainTime.prototype.calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/calendar
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`calendar`** read-only property returns a
{{jsxref('Temporal/Calendar','Temporal.Calendar')}} object
containing the ISO 8601 calendar.No other calendars are currently possible for
{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}, but
the property exists for purposes of future compatibility.

## Syntax

```js
time.calendar
```

### Value

A {{jsxref('Temporal/Calendar','Temporal.Calendar')}} object
containing the ISO 8601 calendar.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.calendar.id;  // => iso8601
// (the only possible calendar for PlainTime)
```
