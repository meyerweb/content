---
title: Temporal.ZonedDateTime.prototype.dayOfWeek
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/dayOfWeek
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`dayOfWeek`** read-only property gives the weekday number on which the
date falls.In the ISO 8601 calendar, the weekday number is defined as in the ISO
8601 standard: a value between `1` and `7`, inclusive, with Monday being `1`,
and Sunday `7`.

## Syntax

```js
datetime.dayOfWeek
```

### Value

An integer representing the weekday number on which the date falls.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2021-04-27');
datetime.dayOfWeek; // => 2
```
