---
title: Temporal.PlainDate.prototype.monthCode
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/monthCode
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>monthCode</code></strong> read-only property returns a calendar-specific string that identifies the month in a year-independent manner.</span></p>

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
date = Temporal.PlainDate.from('2019-02-23');
date.monthCode; // => 'M02'

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.monthCode; // => 'M05L'
```
