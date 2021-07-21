---
title: Temporal.PlainDate.prototype.dayOfWeek
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/dayOfWeek
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`dayOfWeek`** read-only property gives the weekday number on which the
date falls.In the ISO 8601 calendar, this is always a value from `1` to `7`
inclusive, where `1` represents Monday, and `7` represents Sunday, but the range
of values, or alignment of numbers to days, could be different in other
calendars.

## Syntax

```js
date.dayOfWeek
```

### Value

An integer representing the weekday number on which the date falls.

## Examples

```js
date = Temporal.PlainDate.from('2021-04-27');
date.dayOfWeek; // => 2
```
