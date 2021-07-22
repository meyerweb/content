---
title: Temporal.ZonedDateTime.prototype.equals()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/equals
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

This method determines whether a
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object is exactly the same as another zoned date and time.This function exists
because it's not possible to compare using `ZonedDateTime == other` or
`ZonedDateTime === other`, due to ambiguity in the primitive representation and
between Temporal types.

If you also need to know the order in which the two times occur when they are
not equal, use
{{jsxref('Temporal/ZonedDateTime/compare','Temporal.ZonedDateTime.compare()')}}
instead.

## Syntax

```js
equals(otherZonedDateTime)
```

### Parameters

- `otherZonedDateTime`
  - : Another zoned date and time to compare. Either a
    {{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/ZonedDateTime.from()','Temporal.ZonedDateTime.from()')}}.

### Return value

A boolean `true` if the two dates and times are equal; otherwise, `false`. Note
that this function will return `false` if the two date-and-time objects have
different calendar properties, even if the actual dates and times are equal.

Note that two `Temporal.ZonedDateTime` instances can have the same clock time,
time zone, and calendar but still be unequal; e.g., when a clock hour is
repeated after DST (Daylight Saving Time) ends in the Fall. In this case, the
two instances will have different `offsetNanoseconds` property values. To ignore
both time zones and calendars, compare the instants of both:

```js
zdt.toInstant().equals(other.toInstant());
```

## Examples

```js
zdt1 = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500+01:00[Europe/Paris]');
zdt2 = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500+01:00[Europe/Brussels]');
zdt1.equals(zdt2); // => false
 // (same offset but different time zones)
zdt1.equals(zdt1); // => true
```
