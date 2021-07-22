---
title: Temporal.ZonedDateTime constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/constructor
tags:
  - Class
  - JavaScript
  - Time
  - constructor
---
{{JSRef}}

The constructor for a
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object.Instead of the constructor, the
{{jsxref('Temporal/ZonedDateTime/from','from()')}} method is
preferred, because it accepts more kinds of input and provides options for
handling ambiguity and overflow.

## Syntax

```js
new Temporal.ZonedDateTime(epochNanoseconds, timeZone)
new Temporal.ZonedDateTime(epochNanoseconds, timeZone, calendar)
```

### Parameters

- `epochNanoseconds`
  - : A {{jsxref('BigInt')}} number of nanoseconds.
- `timeZone`
  - : The time zone, either a
    {{jsxref('Temporal/TimeZone','Temporal.TimeZone')}} object,
    or a value that can be converted to one with
    {{jsxref('Temporal/TimeZone/from','Temporal.TimeZone.from()')}}.
- `calendar` {{ optional_inline }}
  - : A calendar used to interpret the value of _epochNanoseconds_, in order to
    reckon the date and time by that calendar system.

### Return value

A new
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object. The range of allowed values for this type is the same as the old-style
JavaScript {{jsxref('Date','Date','','nocode')}}: 100 million
(10<sup>8</sup>) days before or after the Unix epoch. This range covers
approximately half a million years. If _epochNanoseconds_ is outside of this
range, a `RangeError` will be thrown.

## Examples

```js
// UNIX epoch in California
new Temporal.ZonedDateTime(0n, Temporal.TimeZone.from('America/Los_Angeles'), Temporal.Calendar.from('iso8601'));
  // => 1969-12-31T16:00:00-08:00[America/Los_Angeles]
new Temporal.ZonedDateTime(0n, 'America/Los_Angeles');
  // => 1969-12-31T16:00:00-08:00[America/Los_Angeles]
  // same, but shorter
```
