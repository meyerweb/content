---
title: Temporal.PlainDateTime.prototype.day
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/day
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`day`** read-only property returns a number that identifies the day of the
month on which the date and time occurs.

## Syntax

```js
datetime.day
```

### Value

A positive integer representing the day of the month.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2019-02-23');
datetime.day; // => 23

datetime = Temporal.PlainDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.day; // => 15
```
