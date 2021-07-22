---
title: Temporal.PlainDateTime.prototype.weekOfYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/weekOfYear
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
datetime.weekOfYear
```

### Value

An integer representing the ISO week number in which the date falls.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2021-04-27');
datetime.weekOfYear; // => 17
```
