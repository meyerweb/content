---
title: Temporal.PlainDate.prototype.inLeapYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/inLeapYear
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
date.inLeapYear
```

### Value

The boolean value `true` if the date occurs in a leap year, or `false` if not.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.inLeapYear; // => false

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.inLeapYear; // => true
```
