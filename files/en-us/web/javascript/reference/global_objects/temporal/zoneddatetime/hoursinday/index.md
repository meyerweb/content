---
title: Temporal.ZonedDateTime.prototype.hoursInDay
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/hoursInDay
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`hoursInDay`** read-only property gives the number of real-world hours
between the start of the current day (usually midnight) to the start of the next
calendar day in the same time zone.Normally days will be 24 hours long, but on
days where there are DST (Daylight Saving Time) changes or other time zone
transitions, this property may return `23` or `25`. In rare cases, other
integers or even non-integer values may be returned; e.g., when time zone
definitions change by less than one hour.

> **Note:** Note that transitions that skip entire days (like the 2011 change of
> `Pacific/Apia` to the opposite side of the International Date Line) will
> return `24`, because there are 24 real-world hours between one day's midnight
> and the next day's midnight.

## Syntax

```js
datetime.hoursInDay
```

### Value

A number representing the number of hours in the date.

## Examples

```js
Temporal.ZonedDateTime.from('2020-01-01T12:00-08:00[America/Los_Angeles]').hoursInDay;
  // => 24
  // (normal day)
Temporal.ZonedDateTime.from('2020-03-08T12:00-07:00[America/Los_Angeles]').hoursInDay;
  // => 23
  // (DST starts on this day)
Temporal.ZonedDateTime.from('2020-11-01T12:00-08:00[America/Los_Angeles]').hoursInDay;
  // => 25
  // (DST ends on this day)
```
