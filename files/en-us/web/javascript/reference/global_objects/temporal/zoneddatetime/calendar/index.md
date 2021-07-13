---
title: Temporal.ZonedDateTime.prototype.calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/calendar
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>calendar</code></strong> read-only property returns an object containing the calendar in which the various date and time
properties of a <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object are interpreted.</span></p>

## Syntax

```js
datetime.calendar
```

### Value

A `{{jsxref('Temporal/Calendar','Temporal.Calendar')}}` object
representing the calendar system used to interpret the
`{{jsxref('Temporal/ZonedDateTime/year','year')}}`,
`{{jsxref('Temporal/ZonedDateTime/month','month')}}`,
`{{jsxref('Temporal/ZonedDateTime/monthCode','monthCode')}}`,
`{{jsxref('Temporal/ZonedDateTime/day','day')}}`,
`{{jsxref('Temporal/ZonedDateTime/hour','hour')}}`,
`{{jsxref('Temporal/ZonedDateTime/minute','minute')}}`,
`{{jsxref('Temporal/ZonedDateTime/second','second')}}`,
`{{jsxref('Temporal/ZonedDateTime/millisecond','millisecond')}}`,
`{{jsxref('Temporal/ZonedDateTime/microsecond','microsecond')}}`,
and
`{{jsxref('Temporal/ZonedDateTime/nanosecond','nanosecond')}}`
properties.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23');
datetime.calendar; // returns a Temporal.Calendar object of the ISO 8601 calendar

datetime = Temporal.ZonedDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.calendar; // returns a Temporal.Calendar object of the Hebrew calendar
```
