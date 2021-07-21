---
title: Temporal.Duration.from()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/from
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`from()`** static method creates a new
{{jsxref('Temporal/Duration','Temporal.Duration')}} object from
another value.

## Syntax

```js
from(duration)
```

### Parameters

- `duration`

  - : A representation of the desired duration. If the value is another
    {{jsxref('Temporal.Duration','Temporal.Duration')}} object,
    a new `Temporal.Duration` object representing the same length of time is
    returned. If the value is any other object, a
    {{jsxref('Temporal.Duration','Temporal.Duration')}} will be
    constructed from the values of any `years`, `months`, `weeks`, `days`,
    `hours`, `minutes`, `seconds`, `milliseconds`, `microseconds`, and
    `nanoseconds` properties that are present. Any missing values are assumed to
    be `0`.

    > **Warning:** All non-zero values must have the same sign, and must not be
    > infinite. Otherwise, the function will throw a `RangeError`. Any
    > non-object value will be converted to a string, which is expected to be in
    > ISO 8601 format. This method understands strings where weeks and other
    > units are combined, and strings with a single sign character at the start,
    > which are extensions to the ISO 8601 standard described in ISO 8601-2. For
    > example, `P3W1D` is understood to mean three weeks and one day, `-P1Y1M`
    > is a negative duration of one year and one month, and `+P1Y1M` is one year
    > and one month. If no sign character is present, then the sign is assumed
    > to be positive.

### Return value

A new {{jsxref('Temporal/Duration','Temporal.Duration')}}
object.

## Examples

```js
d = Temporal.Duration.from({ years: 1, days: 1 }); // => P1Y1D
d = Temporal.Duration.from({ days: -2, hours: -12 }); // => -P2DT12H

Temporal.Duration.from(d) === d; // => false

d = Temporal.Duration.from('P1Y1D'); // => P1Y1D
d = Temporal.Duration.from('-P2DT12H'); // => -P2DT12H
d = Temporal.Duration.from('P0D'); // => PT0S
```

```js example-bad
// Mixed-sign values are never allowed, even if overall positive:
/* WRONG */ d = Temporal.Duration.from({ hours: 1, minutes: -30 }); // => throws
```
