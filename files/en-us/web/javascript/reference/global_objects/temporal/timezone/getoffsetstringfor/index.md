---
title: Temporal.TimeZone.prototype.getOffsetStringFor()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/getOffsetStringFor
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

The **`getOffsetStringFor()`** method returns a formatted string indicating the
UTC offset of a given time.This method is similar to
{{jsxref('Temporal/TimeZone/getOffsetNanosecondsFor','timeZone.getOffsetNanosecondsFor()')}},
but returns the offset formatted as a string.

When subclassing
{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}}, this
method doesn't need to be overridden because the default implementation creates
an offset string using the result of calling
{{jsxref('Temporal/TimeZone/getOffsetNanosecondsFor','timeZone.getOffsetNanosecondsFor()')}}.

## Syntax

```js
getOffsetStringFor(instant)
```

### Parameters

- `instant`
  - : The point in time to yield a time zone offset from UTC. If `instant` is
    not a {{jsxref('Temporal/Instant','Temporal.Instant')}}
    object, then it will be converted to one as if it were passed to
    {{jsxref('Temporal/Instant/from','Temporal.Instant.from()')}}.

### Return value

A formatted string indicating the UTC offset of the given time with sign, hours,
and minutes.

## Examples

```js
// Getting the UTC offset for a time zone at a particular time
timestamp = Temporal.Instant.fromEpochSeconds(1553993100);
tz = Temporal.TimeZone.from('Europe/Berlin');
tz.getOffsetStringFor(timestamp); // => "+01:00"

// TimeZone with a fixed UTC offset
tz = Temporal.TimeZone.from('-08:00');
tz.getOffsetStringFor(timestamp); // => "-08:00"
```
