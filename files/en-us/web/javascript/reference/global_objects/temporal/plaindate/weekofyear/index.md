---
title: Temporal.PlainDate.prototype.weekOfYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/weekOfYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`weekOfYear`** read-only property gives the ISO week number in which the
date falls.In the ISO 8601 and Gregorian calendars, this will be a number from
`1` to `52` or `53` inclusive. ISO week 1 is the week containing the first
Thursday of the year.

## Syntax

```js
date.weekOfYear
```

### Value

An integer representing the ISO week number in which the date falls.

## Examples

```js
date = Temporal.PlainDate.from('2021-04-27');
date.weekOfYear; // => 17
```
