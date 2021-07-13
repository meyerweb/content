---
title: Temporal.PlainDateTime.prototype.month
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/month
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>month</code></strong> read-only property returns a number that identifies the month in which the date and time occurs.</span></p>

## Syntax

```js
datetime.month
```

### Value

A positive integer representing the ordinal index of the month in the current
year. For calendars like Hebrew or Chinese that use leap months, the same-named
month may have a different `month` value depending on the year.

> **Note:** `month` values in Temporal start at `1`, which is different from
> legacy `{{jsxref('Date')}}` where months are represented by zero-based
> indices (0 to 11). Thus, the first month in every year has `month` equal to
> `1`, and the last month of every year has `month` equal to the `monthsInYear`
> property.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2019-02-23');
datetime.month; // => 2

datetime = Temporal.PlainDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.month; // => 6
```
