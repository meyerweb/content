---
title: Temporal.ZonedDateTime.prototype.offsetNanoseconds
slug: >-
  Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/offsetNanoseconds
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`offsetNanoseconds`** read-only property is the offset (in nanoseconds)
relative to UTC of the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object's time zone.The value of this field will change after DST (Daylight
Saving Time) transitions or after political changes to a time zone, e.g. a
country switching to a new time zone.

The `offsetNanoseconds` property is ignored in
{{jsxref('Temporal/ZonedDateTime/with','.with()')}} and
{{jsxref('Temporal/ZonedDateTime/from','.from()')}}. To change
the offset using
{{jsxref('Temporal/ZonedDateTime/with','.with()')}} (or
{{jsxref('Temporal/ZonedDateTime/from','from()')}} using an
object instead of a string), use the string-typed
{{jsxref('Temporal/ZonedDateTime/offset','offset')}} property.

## Syntax

```js
datetime.offsetNanoseconds
```

### Value

An integer.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('2020-11-01T01:30-07:00[America/Los_Angeles]');
zdt.offsetNanoseconds;
  // => -25200000000000
  // (-7 * 3600 * 1e9)
```
