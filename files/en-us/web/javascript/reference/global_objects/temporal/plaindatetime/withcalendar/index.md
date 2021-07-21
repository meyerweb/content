---
title: Temporal.PlainDateTime.prototype.withCalendar()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/withCalendar
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`withCalendar()`** method returns a
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object of a date projected into a specified calendar.

## Syntax

```js
withCalendar(calendar)
```

### Parameters

- `calendar`
  - : The calendar into which to project the date. Can be represented by a
    {{jsxref('Temporal.Calendar','Temporal.Calendar')}} object,
    an object that implements the Temporal calendar protocol, or a string
    identifying a calendar.

### Return value

A new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object representing the date projected into the specified calendar.

## Examples

```js
date = Temporal.PlainDateTime.from('2006-08-24T03:24:30.000003500');
jaDate = date.withCalendar('japanese');
ilDate = date.withCalendar('hebrew');

jaDate.day;     // => 24
jaDate.month;   // => 8
jaDate.year;    // => 2006
jaDate.era;     // => "heisei"
jaDate.eraYear; // => 18
jaDate.hour;    // => 3
jaDate.minute;  // => 24
jaDate.second;  // => 30
jaDate.millisecond; // => 0
jaDate.microsecond; // => 3
jaDate.nanosecond;  // => 500


ilDate.day;     // => 30
ilDate.month;   // => 11
ilDate.year;    // => 5766
ilDate.era;     // => undefined
ilDate.eraYear; // => undefined
ilDate.hour;    // => 3
ilDate.minute;  // => 24
ilDate.second;  // => 30
ilDate.millisecond; // => 0
ilDate.microsecond; // => 3
ilDate.nanosecond;  // => 500
```
