---
title: Temporal.PlainDateTime.prototype.monthCode
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/monthCode
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`monthCode`** read-only property returns a calendar-specific string that
identifies the month of the date and time in a year-independent manner.

## Syntax

```js
datetime.monthCode
```

### Value

A string containing a calendar-specific string that identifies the month in a
year-independent way.

For common (non-leap) months, `monthCode` should be `M{month}`, where `{month}`
is zero-padded up to two digits. For uncommon (leap) months in lunisolar
calendars like Hebrew or Chinese, the month code is the previous month's code
with with an `L` suffix appended.

Examples: `'M02'` is returned for February; `'M08L'` is returned for the
repeated 8th month in the Chinese calendar; `'M05L'` is returned for Adar I in
the Hebrew calendar.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2019-02-23');
datetime.monthCode; // => 'M02'

datetime = Temporal.PlainDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.monthCode; // => 'M05L'
```
