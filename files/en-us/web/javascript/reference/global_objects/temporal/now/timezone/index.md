---
title: Temporal.now.timeZone()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/timezone
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - now
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

The **`timeZone()`** method gets the current system time zone.

## Syntax

```js
timeZone()
```

### Parameters

None.

### Return value

A `Temporal.TimeZone` object representing the current system time zone. This
will often be a named [IANA time zone](https://www.iana.org/time-zones) (e.g.,
`Europe/Madrid` or `Africa/Kigali`) as that is how most people configure their
computers, but other values are possible.

## Example

```js
// When is the next daylight saving change from now, in the current location?
tz = Temporal.now.timeZone();
now = Temporal.now.instant();
nextTransition = tz.getNextTransition(now);
before = tz.getOffsetStringFor(nextTransition.subtract({ nanoseconds: 1 }));
after = tz.getOffsetStringFor(nextTransition.add({ nanoseconds: 1 }));
console.log(`At ${nextTransition.toZonedDateTimeISO(tz)} the offset will change from UTC ${before} to ${after}`);
// example output:
// At 2021-03-14T03:00:00-07:00[America/Los_Angeles] the offset will change from UTC -08:00 to -07:00
```
