---
title: Temporal.PlainDateTime.prototype.calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/calendar
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>calendar</code></strong> read-only property returns an object containing the calendar in which the various date and time
properties of a <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code> object are interpreted.</span></p>

## Syntax

```js
datetime.calendar
```

### Value

A `{{jsxref('Temporal/Calendar','Temporal.Calendar')}}` object
representing the calendar system used to interpret the
`{{jsxref('Temporal/PlainDateTime/year','year')}}`,
`{{jsxref('Temporal/PlainDateTime/month','month')}}`,
`{{jsxref('Temporal/PlainDateTime/day','day')}}`,
`{{jsxref('Temporal/PlainDateTime/hour','hour')}}`,
`{{jsxref('Temporal/PlainDateTime/minute','minute')}}`,
`{{jsxref('Temporal/PlainDateTime/second','second')}}`,
`{{jsxref('Temporal/PlainDateTime/millisecond','millisecond')}}`,
`{{jsxref('Temporal/PlainDateTime/microsecond','microsecond')}}`,
and
`{{jsxref('Temporal/PlainDateTime/nanosecond','nanosecond')}}`
properties.

## Examples

```js
datetime = Temporal.PlainDateTime.from('2019-02-23');
datetime.calendar; // returns a Temporal.Calendar object of the ISO 8601 calendar

datetime = Temporal.PlainDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.calendar; // returns a Temporal.Calendar object of the Hebrew calendar
```
