---
title: Temporal.TimeZone constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/constructor
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - constructor
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

The constructor for a
{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}} object.Use
this constructor directly if you have a string that is **known** to be a correct
time zone identifier, or else represents a UTC offset. If you have an ISO 8601
date-time string,
{{jsxref("Temporal/TimeZone/from","Temporal.TimeZone.from()")}}
is probably more convenient.

**NOTE:** The returned time zone object behaves slightly differently depending
on whether an IANA time zone name (e.g. `Europe/Berlin`) is given, or a UTC
offset (e.g. `+01:00`). IANA time zones may have associated DST transitions, and
UTC offsets do not.

## Syntax

```js
new Temporal.TimeZone(timeZoneIdentifier)
```

### Parameters

- `timeZoneIdentifier`
  - : A string which is canonicalized before being used to determine the time
    zone. For example, values like `+01` will be understood to mean `+01:00`,
    and capitalization will be corrected. If no time zone can be determined from
    `timeZoneIdentifier`, then a `RangeError` is thrown.

### Return value

A new {{jsxref('Temporal/TimeZone','Temporal.TimeZone')}}
object.

## Examples

```js
tz = new Temporal.TimeZone('UTC');
tz = new Temporal.TimeZone('Africa/Cairo');
tz = new Temporal.TimeZone('america/VANCOUVER');
tz = new Temporal.TimeZone('Asia/Katmandu'); // alias of Asia/Kathmandu
tz = new Temporal.TimeZone('-04:00');
tz = new Temporal.TimeZone('+0645');
```

```js example-bad
/* WRONG */
tz = new Temporal.TimeZone('local'); // throws, not a time zone
```

```js
tz1 = new Temporal.TimeZone('-08:00');
tz2 = new Temporal.TimeZone('America/Vancouver');
inst = Temporal.ZonedDateTime.from({ year: 2020, month: 1, day: 1, timeZone: tz2 }).toInstant();
tz1.getNextTransition(inst); // => null, UTC offsets do not have DST schedules
tz2.getPreviousTransition(inst); // => 2020-03-08T10:00Z
```
