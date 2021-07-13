---
title: Temporal.PlainDate.prototype.calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/calendar
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>calendar</code></strong> read-only property returns an object containing the calendar in which the <code>{{jsxref('Temporal/PlainDate/year','year')}}</code>, <code>{{jsxref('Temporal/PlainDate/month','month')}}</code>, and <code>{{jsxref('Temporal/PlainDate/day','day')}}</code> properties are interpreted.</span></p>

## Syntax

```js
date.calendar
```

### Value

A `{{jsxref('Temporal/Calendar','Temporal.Calendar')}}` object
representing the calendar system used to determine the year, month, and day.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.calendar; // returns a Temporal.Calendar object of the ISO 8601 calendar

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.calendar; // returns a Temporal.Calendar object of the Hebrew calendar
```
