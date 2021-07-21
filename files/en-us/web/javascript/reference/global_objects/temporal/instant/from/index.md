---
title: Temporal.Instant.from()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/from
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

The **`from()`** static method creates a
{{jsxref('Temporal/Instant','Temporal.Instant')}} object from
another such object, or from a string, representing a specific point in time.

## Syntax

```js
from(moment)
```

### Parameters

- `moment`

  - : Either a {{jsxref('Temporal/Instant','Temporal.Instant')}}
    object, or a string value.

    If `moment` is another
    {{jsxref('Temporal/Instant','Temporal.Instant')}} object, the
    returned object represents the exact same time. Any other value is converted
    to a string, which is expected to be in ISO 8601 format, including a date, a
    time, and a time zone. The time zone name, if given, is ignored; only the
    time zone offset is taken into account.

### Return value

A new {{jsxref('Temporal/Instant','Temporal.Instant')}} object.

## Examples

```js
instant = Temporal.Instant.from('2019-03-30T01:45:00+01:00[Europe/Berlin]');
instant = Temporal.Instant.from('2019-03-30T01:45+01:00');
instant = Temporal.Instant.from('2019-03-30T00:45Z');
instant === Temporal.Instant.from(instant); // => true

// Not enough information to denote an exact time:
/* WRONG */ instant = Temporal.Instant.from('2019-03-30'); // no time; throws
/* WRONG */ instant = Temporal.Instant.from('2019-03-30T01:45'); // no time zone; throws
```
