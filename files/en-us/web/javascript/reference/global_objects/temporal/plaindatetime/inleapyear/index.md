---
title: Temporal.PlainDateTime.prototype.inLeapYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/inLeapYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`inLeapYear`** read-only property indicates whether the date occurs in a
leap year.

## Syntax

```js
datetime.inLeapYear
```

### Value

The boolean value `true` if the date occurs in a leap year, or `false` if not.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2019-02-23T01:23:45');
datetime.inLeapYear; // => false

datetime = Temporal.PlainDateTime.from('2019-02-23T01:23:45[u-ca=hebrew]');
datetime.inLeapYear; // => true
```
