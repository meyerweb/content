---
title: Temporal.ZonedDateTime.prototype.toPlainDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toPlainDateTime
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`toPlainDateTime()`** method returns a new
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object that corresponds to the date and time (but not time zone) components of
the
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object.

**NOTE:** After a
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
is converted to
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}},
the resulting object will no longer be aware of its time zone. This means that
subsequent operations using methods like `.add()`, `.subtract()`, and `.with()`
will not adjust for DST (Daylight Saving Time) and may not yield the same
results as equivalent operations with
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}.
However, unless you perform those operations across a time zone offset
transition, it's impossible to notice the difference. Therefore, be very careful
when performing this conversion because subsequent results may look correct most
of the time, but fail around time zone transitions like when DST starts or ends.

## Syntax

```js
toPlainDateTime()
```

### Parameters

None.

### Return value

A new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Johannesburg]');
zdt.toPlainDateTime(); // => 1995-12-07T03:24:30
```
