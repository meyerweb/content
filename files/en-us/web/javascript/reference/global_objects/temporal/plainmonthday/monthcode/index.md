---
title: Temporal.PlainMonthDay.prototype.monthCode
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/monthCode
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`monthCode`** read-only property returns a calendar-specific string that
identifies the month in a year-independent manner.

Note that
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
has no `month` property, because month numbers are ambiguous for some calendars
without knowing the year. Instead, the `monthCode` property is used which is
year-independent in all calendars.

## Syntax

```js
date.monthCode
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
md = Temporal.PlainMonthDay.from('08-24');
md.monthCode; // => 'M08'

md = Temporal.PlainMonthDay.from('2019-02-20[u-ca=hebrew]');
md.monthCode; // => 'M05L'
```
