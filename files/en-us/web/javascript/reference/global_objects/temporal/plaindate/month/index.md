---
title: Temporal.PlainDate.prototype.month
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/month
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`month`** read-only property returns a number that identifies the month in
which the date occurs.

## Syntax

```js
date.month
```

### Value

A positive integer representing the ordinal index of the month in the current
year. For calendars like Hebrew or Chinese that use leap months, the same-named
month may have a different `month` value depending on the year.

> **Note:** `month` values in Temporal start at `1`, which is different from
> legacy {{jsxref('Date')}} where months are represented by zero-based
> indices (0 to 11). Thus, the first month in every year has `month` equal to
> `1`, and the last month of every year has `month` equal to the `monthsInYear`
> property.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.month; // => 2

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.month; // => 6
```
